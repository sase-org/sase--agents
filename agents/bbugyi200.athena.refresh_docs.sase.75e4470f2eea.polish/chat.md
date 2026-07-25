# Chat History - ace-run

- **TIMESTAMP:** 2026-07-06 11:16:35 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** refresh_docs.sase.75e4470f2eea.polish

## Prompt

%wait:refresh_docs.sase.75e4470f2eea.update
%name:refresh_docs.sase.75e4470f2eea.polish
#gh:gh_sase-org__sase %g:chop #fork:refresh_docs.sase.75e4470f2eea.update

Inspect the documentation changes made by the first refresh-docs agent.
Verify descriptions against the current system behavior rather than assuming they are true.
Improve clarity for a new user, especially where terminology or workflow ordering could be misunderstood.
Keep edits scoped to documentation unless a tiny companion correction is required.
If you change files, run the appropriate documentation checks for this repository. %m:claude/claude-fable-5

## Response

I'll review the docs commit `2b4d8e9ae` made by the previous agent, verifying its claims against the actual code. Let me start by looking at the full diff.

Now the new page — the biggest piece to verify:

I'll start by reading the documentation file and the key code files in parallel.

Now let me read the loading logic, the bundled examples, the xprompt_handler, and plan_chain reserved suffixes.

I'll investigate these claims by reading the relevant files. Let me start by exploring the codebase structure and reading key files in parallel.

Now let me check plan_chain.py suffixes, xprompt_handler.py, load_issues, and the evaluator code.

Now let me read the plan approval choices and related files in parallel.

Now let me read the config files, agent_family definitions, agent model, and docs.

Let me read the xprompt_handler output section and the evaluator for ordering claims.

I'll explore the relevant files in parallel to verify these documentation claims.

Let me explore the custom_definitions directory and read config/docs/agent model files.

Let me read the core files in parallel.

Let me verify the role_completed firing ordering (claim 9) and the "chain after itself" guard.

Let me read the custom_definitions models, the plan approval modal, the evaluator for loop caps, and docs/ace.md.

I'll start by exploring the relevant files mentioned in the claims.

Now let me look at the docs, launch_preview, notification action dispatch, and family-related code in parallel.

Let me read the key files for the claims in parallel.

Now let me read the docs context and find the ACE notification action dispatch, plus the family-related code.

I'll verify each claim against the actual code. Let me start by exploring the relevant files in parallel.

Now let me examine the evaluator for loop caps, the validation for max_visits default, docs/ace.md, and search for remote/archive behavior.

Now let me look at the config, models panel, onboarding widgets, and other files.

Let me read the archive function, the notification sender context, and the evaluator.

Claim 1 confirmed: choices are `("dev", "pypi")`, no `auto`. Let me continue with the mode_switch modules, config, and other files.

Now let me check the leader mode dispatch, tab default, onboarding widgets, and header summary.

Anchors resolve. `just install` finished. Now let me verify the `#with_feedback::` example syntax used in the new page against the xprompt docs and parser:

Let me verify the package xprompts dir path and read the .md prompt templates to finalize claims 4 and 8.

Let me read the archive gating in plan_approval_actions.py and check remote choice usage.

Let me read the LaunchApproval modal flow, the notification sender for priority, the mobile launch path, and the agent_families.md claims.

Let me find the CLI `-t/--tab` flag definition and check the onboarding widgets.

Now let me check the config, xprompts research file, bead parser, init parser, and TUI files.

Let me check the parser for the tab default and the other onboarding widgets and header summary.

Let me read the evaluator for loop caps and search for remote/telegram approval rendering.

Let me read the parser tab default, axe_onboarding, and the header summary, plus check LaunchApproval and where the onboarding is shown (empty-state conditions).

Let me check the notify_launch_approval sender for priority, the write_workflow_action_response dispatch, and the agent_families.md claims plus evaluator code.

Let me read the docs/ace.md options dialog section and search for remote approval button construction.

Now let me look at the slow-tool-calls display header and where the onboarding empty-states are triggered.

Now let me find the bead list handler, TUI panes, model completion, and plugin handlers.

Let me find where the slow tool sources are actually rendered into header text.

Let me verify the "priority notification" concept and the standard_plan_chain evaluator with typed events.

Let me check the priority.py logic and the standard_plan_chain_evaluator for typed events.

Let me search for remote choices usage and how default_member_ids flow into the notification.

Let me verify the `on_done: re_review` handling and prompt_template format placeholders.

Let me verify the event definitions and the agent_meta snapshot fields.

Let me check where the slow tool calls section is placed (the "metadata header"), and verify the onboarding empty-state trigger conditions and plugin detection.

Let me verify the agent_meta.json snapshot fields are actually written/tracked.

Let me read the custom roles spawn file to verify format placeholders and on_done handling.

Let me read the plan notification builder and search for telegram/mobile action button construction.

Now let me check the TUI panes, plugin handlers, list_issues sort order, and alias constants.

Let me search for where `on_done`/`re_review` behavior is actually consumed to verify the "back into plan gate" claim.

Let me confirm the role_completed emission condition and FamilyStateSnapshot fields.

Let me find where the ChangeSpec onboarding empty-state is triggered and where the launch hint / launch_targets_available is set.

Let me check the exact role_completed emission context to confirm the "un-killed" condition and terminate mapping.

Let me search for how remote plan-approval responses are produced and where "run" choice is consumed.

Let me find where the ChangeSpec onboarding panel is shown/hidden (the empty-state condition).

Let me read the mobile notification actions integration.

Let me read the BINDINGS block, plugin handlers for restart behavior, and list_issues sort.

Let me read the top of plan_approval_actions.py to confirm the response flow for the "run" choice.

list_issues sorts `ORDER BY created_at ASC`, so `issues[-limit:]` = newest 20 by creation. Now let me trace the plugin restart behavior.

Let me verify how the agent counts (N total and starting) are computed by the caller, to check claim 4.

Let me quickly confirm `sase_subdir` maps to `~/.sase` for claim 5.

Let me confirm the bundled package `.md` xprompts are actually loaded into the xprompt catalog (relevant to claim 8).

Let me verify claim 11's role classification logic in plan_chain.py.

Let me verify the `format_remaining_until` output format for the violet pill (claim 6).

All claims verified. Here is the numbered verdict list.

## Verdicts

**1. CORRECT** — Gating is on the `SASE_AGENT` env var, not something else.
- `running_agent_context_requires_launch_approval()` returns `bool(os.environ.get("SASE_AGENT"))` — `src/sase/agent/launch_request.py:185-187`.
- The `sase run` handler diverts into a LaunchApproval request only when that returns true — `src/sase/main/query_handler/_launch.py:47-59`.
- TUI launches call `launch_agents_from_cwd(...)` directly with no gate; Telegram/mobile calls `launch_agents_from_cwd(prompt)` directly with no gate — `src/sase/integrations/_mobile_agent_launch.py:84`. So user prompts (no `SASE_AGENT` set) spawn directly, including user-typed `%n(...)`.

**2. CORRECT** — The skill teaches writing a JSON request and submitting with exactly `sase launch request -f launch_request.json -o json` — `src/sase/xprompts/skills/sase_run.md:14-30`.

**3. CORRECT** — `src/sase/agent/launch_request.py:190-243`: `schema_version` must equal 1 (191-197); `prompt` required (199-201); `reason` optional, defaults to `"Detached launch requested."` (203-207); `approval` must be `"required"` — any other value raises `unsupported_approval` (209-215); `max_slots` default 1, must be ≥1 (217-227); `family_type` optional string (236-242). On over-fan-out, `create_launch_approval_request` raises `LaunchRequestError("max_slots_exceeded", ...)` when `slot_count > max_slots` — the request is rejected, not truncated — `src/sase/agent/launch_request.py:83-90`.

**4. CORRECT** — Inline positional `payload` supports raw JSON and `@PATH` (`parser_launch.py:56-60`; `@` handled in `launch_handler.py:76-77`). Flags all present: `-a/--approval` default `required` (61-66), `-f/--file`→`payload_file` (67-72), `-m/--max-slots` int default 1 (73-79), `-o/--output` choices `("text","json")` default `text` (80-86), `-p/--prompt` (87-91), `-r/--reason` (92-96), `-s/--source` (97-101) — `src/sase/main/parser_launch.py`.

**5. CORRECT** — Request ids are `f"launch-{uuid4()}"` (`launch_preview.py:26-28`); artifacts written to `sase_subdir("launch_requests")/request_id` (`launch_preview.py:116-118`), and `sase_subdir` resolves to `$SASE_HOME` or `~/.sase/<subdir>` (`src/sase/core/paths.py:49-53`). `launch_request.json` holds the full preview payload plus `request["launch_request"] = normalized` (`launch_request.py:99`), and `launch_preview.md` is the rendered human preview (`launch_preview.py:120-127, 138-179`).

**6. CORRECT** — Skill documents embedding `%n(parent, reviewer)` / `%n(parent, @)` in the prompt (`sase_run.md:19,37-45`). The prompt is preserved through `_build_preview_plan` (which expands multi-agent xprompts) and stored in `dispatch.prompt`, then re-processed at dispatch via `launch_agents_from_cwd` — not stripped (`launch_request.py:99-104, 246-294, 173-175`).

**7. CORRECT** — Modal BINDINGS: `a`=approve, `r`=reject, `q` and `escape`=cancel (`launch_approval_modal.py:30-39`); `_read_preview()` renders the attached preview file (`96-102`), and the handler selects the file ending in `launch_preview.md` (`_notification_modals.py:243-246`).

**8. CORRECT** — `parser_launch.py:22-45` defines `approve <selector>` and `reject <selector>` with `-f/--feedback`. `_resolve_launch_notification` matches on `notification.id == selector`, `notification.id.startswith(selector)`, or `action_data["request_id"] == selector` — i.e. notification id, unique notification prefix, or request id (`launch_handler.py:130-151`).

**9. CORRECT** — Write-once: response written with open mode `"x"`; a second attempt raises `conflict_already_handled` (`launch_approval_actions.py:160-172`), and CLI also pre-checks the `already_handled` state (`launch_handler.py:154-167`). On approval, `dispatch_approved_launch_request` re-reads and re-validates the request/dispatch payload then calls `launch_agents_from_cwd(prompt)` (the normal launch path, which re-plans) (`launch_request.py:128-182`). Preview marks `all_or_nothing: True` (`launch_preview.py:88`). Rejection writes `feedback` into `launch_response.json` for the requesting agent to poll (`launch_approval_actions.py:145-154`; skill poll instructions `sase_run.md:48-63`).
- Minor note: all-or-nothing rollback is a property of the shared `launch_agents_from_cwd`/multi-prompt launcher path; `dispatch_approved_launch_request` itself does not add extra rollback beyond propagating the error. The doc claim is still accurate.

**10. CORRECT** — Row exists verbatim: `LaunchApproval | Agent | Opens the launch approval modal for an agent-requested launch` (`docs/ace.md:1097`). It is a real dispatched action: `elif result.action == "LaunchApproval": handle_launch_approval(...)` (`_notification_modal_flow.py:192-193`), which pushes `LaunchApprovalModal` (`_notification_modals.py:228-289`). Priority claim holds: `LaunchApproval` is in `_PRIORITY_ACTIONS` so `is_priority()` returns true (`src/sase/notifications/priority.py:11-13,39-40`); doc says "arrive as priority notifications" (`docs/ace.md:1637`).

**11. CORRECT** — `HandoffEventKind = Literal["plan_submitted","questions_submitted","role_completed"]` (`standard_plan_chain_definition.py:26-30`), routed by `evaluate_handoff_event` in the standard-chain evaluator (`standard_plan_chain_evaluator.py:181-219`). `role_completed` has `terminal=True` → maps to terminate (`standard_plan_chain_definition.py:209-215`). It fires for follow-ups completing un-killed: `_handle_completed_followup` builds the `role_completed` event only when `agent_step > 1` and a role suffix exists, on the `not was_killed()` completion path (`run_agent_exec.py:204-220, 324-338`). Snapshot fields written to `agent_meta.json` via `as_meta_fields`: `agent_family_config_id`/`_version`/`_hash`, `family_state` (with `current_role`, `feedback_count`, `qa_round_count`, `visit_counts`), and `agent_family_custom_role` for custom-role members (`standard_plan_chain_models.py:68-79`; `FamilyStateSnapshot.as_json` `30-38`).

All 11 claims are accurate as written; no corrections required.

Let me verify the Updates tab display of current mode and dev root, and confirm sase update JSON uses the same restart shape.

Let me do final checks on the research xprompt registry, skill init parser, and the ACE restart behavior.

Let me verify the TUI archive path, cap-exhausted recording, and custom_role_label population.

Let me check custom_role_label population source and the terminal_reason/exhausted-role artifact recording.

Let me read the cap-exhausted handler in the agent exec plan accept.

Let me verify the source of the custom-role label metadata (role definition vs launch site).

I have gathered enough evidence. Let me verify one final detail on where the slow-tool section renders in the header.

I have all the evidence needed. Here are my verdicts.

---

## Verdicts

**1. "YAML recognized as family definition only when top-level `kind: agent_family`."**
**CORRECT.** `loading.py:52-55` — `if not isinstance(data, Mapping): return None` then `if data.get("kind") != "agent_family": return None`. Non-matching files are silently ignored (not even a load issue). `is_agent_family_definition_mapping` (`loading.py:69-72`) confirms the same key.

**2. Top-level fields.**
**CORRECT.** All confirmed in `validation.py`:
- `schema_version` must be `1`: `:68-70` (`if schema_version != 1: raise`).
- `id` matching `^[A-Za-z][A-Za-z0-9_]*$`: `_ROLE_ID_RE` `:26` via `_required_role_like_id` `:71,237-243`.
- `version` positive int: `:72,252-255`.
- `extends` optional, only `standard_plan_chain`, default: `:73-77` (`str(data.get("extends") or STANDARD_EXTENDS_ID)`, rejects anything else). `STANDARD_EXTENDS_ID` is `"standard_plan_chain"` (imported from models; example files use it and validate).
- `roles` required non-empty mapping keyed by role id: `:78-80`.
- `kind` is the recognition gate (`loading.py:54`), not re-validated in parse — consistent with the table.

**3. Per-role fields.**
**CORRECT on every field-validation spec; IMPRECISE on one behavioral parenthetical (`re_review`).**
- Unknown keys are load errors: `validation.py:169-172`.
- `suffix` default `--<role_id>`, regex `^--[A-Za-z0-9_]+$`, reserved-collision check: `_parse_suffix :294-314`, `_CANONICAL_SUFFIX_RE :27`, `_RESERVED_SUFFIXES :28-35` (`--plan/--q/--code/--epic/--legend/--commit`).
- `prompt_template` required + validated against catalog: `:174-184,330-347`. Format placeholders confirmed exactly as `plan_file, source_artifacts, artifacts_ref, outcome, source_role, role` — `run_agent_exec_custom_roles.py:53-62` (`format_map`; `role=role.id`).
- `placement.after` required: `_parse_placement :317-327`. `after: plan` binds to plan gate: `standard_plan_chain_evaluator.py:312-327` (`_select_custom_role_after("plan", ...)`). `after: code`/terminal binds to role completion: `run_agent_exec.py:210-241`.
- `on_done` required `re_review|continue|terminate`: `:186-190`. **However** — the value is only validated, snapshotted (`models.py:24,43`), and displayed in `sase xprompt list` (`xprompt_handler.py:174`). A grep of the entire `src/` shows **no runtime consumer branches on `on_done`/`re_review`.** The re-review loop is actually produced by the prompt template telling the agent to resubmit a plan via `/sase_plan` (see `agent_family_improve_plan.md:15`), not by `on_done` routing "output back into the plan gate." So that parenthetical describes intent, not an implemented `on_done` mechanism.
- `on_failure` required `notify_and_continue|notify_and_stop`: `:191-195`.
- `auto` required `run|skip`, no default (missing → rejected): `:196-200` (`_literal_value(raw_role.get("auto"), ...)`).
- `max_visits` optional positive int default 3; cap hard-stops + terminates: `:205-208`; `standard_plan_chain_evaluator.py:133-139` (`prior_visits >= role.max_visits → cap_exhausted=True`) → `:200-205` (`terminal=True`, `terminal_reason="custom_role_cap_exhausted"`).
- `default` optional bool default false: `:201-204`.
- `label`/`done_label` ≤24 chars, regex `^[A-Za-z0-9][A-Za-z0-9 _/-]*$`, display-only: `_DISPLAY_LABEL_RE :53`, `_DISPLAY_LABEL_MAX_LEN=24 :54`, `_optional_display_label :275-291`.
- `delegated_budget(s)` reserved/snapshotted/not interpreted: `_ROLE_KEYS :47-51`, `_RESERVED_ROLE_KEYS :52`, `reserved` dict built + stored `:214-233`.

**4. Discovery order + globbing.**
**CORRECT.** `discovery.py:41-72` runs in exactly the doc's order, each via `definitions.update()` (later wins by id): (1) `get_sase_package_xprompts_dir()` `:41-47`; (2) plugin `sase_xprompts` `:48-53,177`; (3) `~/.config/sase/xprompts/<project>/` `:135-145`; (4) workspace `.xprompts/` + `xprompts/` `:148-165`; (5) general search paths `:67-72,118-132` (iterates `reversed(get_xprompt_search_paths())` so highest-priority path applies last/wins). Files matched via `directory.glob("*.yml"|"*.yaml")` in `_load_definitions_from_dir :104` — "same directories as xprompts."

**5. Skip format string.**
**CORRECT.** `xprompt_handler.py:198` — `print(f"skipped: {issue.source}: {issue.error}", file=sys.stderr)`. Exactly `skipped: <source>: <error>`. Issues recorded via `record_load_issue` (`loading.py:30,33,65`).

**6. Valid defs in `sase xprompt list` with `"type": "agent_family"` + role-summary preview.**
**CORRECT.** `xprompt_handler.py:181-194` — `"type": "agent_family"` (`:184`), and `"preview": json.dumps({"roles": roles}, sort_keys=True)` (`:193`) where each role carries `id, suffix, placement_after, prompt_template, on_done, max_visits, on_failure, auto` (`:168-179`).

**7. Bundled examples: location, inactivity, exact contents.**
**CORRECT.** Files at `src/sase/xprompts/examples/agent_families/improve_plan.yml` and `tester.yml`. They are outside discovery: discovery globs the top-level package dir non-recursively (`glob("*.yml")`), so the `examples/agent_families/` subdirectory is never scanned, and no other source targets it. Contents match the doc **field-for-field**, including quoted values: improve_plan.yml (`:1-18`) has all 14 doc values verbatim; tester.yml (`:1-18`) likewise (`--tester`, `TESTING`/`TESTED`, `agent_family_tester:{source_artifacts}`, `after: code`, `on_done: terminate`, `max_visits: 1`, `on_failure: notify_and_continue`, `auto: run`). No divergence.

**8. "Copy one … together with its prompt-template xprompt … to enable it."**
**WRONG (misleading).** The prompt-template xprompts are already bundled and active by default, so the user does **not** need to copy the `.md`. `agent_family_improve_plan.md` and `agent_family_tester.md` live directly in `src/sase/xprompts/` (not in `examples/`). That directory is `get_sase_package_xprompts_dir()` (`loader_sources.py:123-137`) and its `*.md` files are loaded as built-in xprompts: `loader_sources.py:265-271` (`internal_dir = get_sase_package_xprompts_dir(); md_files = [*sorted(internal_dir.glob("*.md"))]`). Correct fact: only the example `.yml` needs to be copied into an active xprompts dir; its referenced prompt template is already packaged/discoverable (which is also why prompt-ref validation passes without copying anything).

**9. Post-code members run after coder's embedded `#propose`/`#commit`; tester doesn't block propose.**
**CORRECT.** `role_completed` is emitted only after the follow-up workflow fully returns — `run_agent_exec.py:204-241` (`_handle_completed_followup` builds the `role_completed` event on normal completion, then selects `after: code` custom roles). The propose/commit steps are embedded inside the coder workflow, so they finish before `role_completed` fires. Documented explicitly at `standard_plan_chain_models.py:45-47`: "`role_completed` is emitted after the follow-up workflow returns, so a later post-code role naturally sequences after reconstructed embedded VCS refs such as `#propose` and `#commit`."

**10. "A custom role can never chain directly after itself."**
**CORRECT** (and the guard is actually broader). `standard_plan_chain_evaluator.py:164-172` — for a `role_completed` event, if the just-completed agent carries a custom-role snapshot and `event.interrupted_role == snapshotted_role.id`, it returns `None` (no follow-up). Since a completing custom role's snapshot id always equals its own `interrupted_role`, this blocks self-chaining (and in fact any custom role from being an `after:` target via role_completed). The doc's narrower statement is accurate.

**11. Family-roles table + reserved-suffix source.**
**CORRECT.** `plan_chain.py:10-15` defines the reserved suffixes (`--plan/--q/--code/--epic/--legend/--commit`) — this is the source imported by `validation.py:16-24`. Built-in role mapping: `_PHASE_SUFFIX_ROLES :50-56` + question suffix `:181-187`. Numeric feedback rounds: `_FEEDBACK_SUFFIX_RE = ^(?:--|[-.])(\d+)$` `:21` → `role="feedback"` `:189-196` (the `@` form is the template that materializes into these numeric rounds, e.g. `question_followup_suffix_template` returns `--@`). Open-set custom word recorded in `agent_family_role` metadata: `_stored_family_role :99-104` accepts any `_TOKEN_RE` word and `_parse_plan_chain_suffix :226-233` returns `role=stored_role`, resolved via `agent_family_role_for_suffix :354-361`.

---

### Summary of problems found
- **Claim 8 is WRONG/misleading:** the prompt-template `.md` xprompts (`agent_family_improve_plan.md`, `agent_family_tester.md`) are bundled in `src/sase/xprompts/` and active by default; the user only needs to copy the example `.yml`, not "its prompt-template xprompt too."
- **Claim 3 caveat:** the `on_done: re_review` "sends output back into the plan gate" note is not implemented as an `on_done`-driven mechanism — `on_done` is validated/snapshotted/displayed but has no runtime consumer; the re-review loop is driven by the prompt template resubmitting a plan. All other field specs in claim 3 are correct.
- Everything else (claims 1, 2, 4, 5, 6, 7, 9, 10, 11) is CORRECT.

I have all the evidence needed. Here are the verdicts.

## Verdict list

**1. Tab order Agents → PRs → AXE; Agents first and startup default — CORRECT**
- `src/sase/ace/tui/tab_order.py:16` — `TAB_ORDER = ("agents", "changespecs", "axe")`. The "changespecs" tab is labeled "PRs" (`tab_guide_modal.py:17` maps `changespecs`→`"PRs Guide"`; `agent_onboarding.py:43-46` maps `changespecs`→`"PRs"`), so left-to-right is Agents → PRs → AXE, and `adjacent_tab` cycles that order.
- Startup default is Agents: `src/sase/ace/tui/app.py:208` (`initial_tab: TabName = "agents"`) and `src/sase/main/parser_ace.py:61-66` (`--tab ... default="agents"`).

**2. Leader `?` guide modal, `,?` notation, all three tabs — CORRECT**
- Config key: `src/sase/default_config.yml:205` — `tab_guide: "question_mark"`, under `leader_mode` whose `prefix: "comma"` (`:202`). So the chord is comma-then-`?` = `,?` — correct notation.
- Dispatch is ungated by tab: `src/sase/ace/tui/actions/agent_workflow/_leader_mode.py:71-75` opens the modal for `self.current_tab` on any tab; `_open_tab_guide_modal` at `:264-286`.
- The modal shows the current tab's onboarding guide widget (`tab_guide_modal.py:56-77`), which does summarize what the tab shows plus key bindings (see onboarding widgets). Works on all three tabs.

**3. Onboarding claims — CORRECT (all four)**
- (a) PRs card shown only when no ChangeSpecs AND no saved queries: `src/sase/ace/tui/actions/changespec/_onboarding.py:17-23` — returns False if `_all_changespecs` non-empty, else `not bool(_saved_queries)`. CORRECT.
- (b) Agents onboarding walks through launching, launch hint conditional: `agent_onboarding.py:28-33` step title "Launch your first agent"; `_build_launch_card` at `:234-251` always shows the home-workspace launch instruction, and the project/CL launch-target hint only renders when `launch_targets_available` (`:244-247`), toggled via `set_launch_targets_available` (`:126-133`). CORRECT (note: the primary home-workspace launch line always shows; only the project/CL hint is gated).
- (c) Recommends installing plugins from Admin Center when no third-party plugins: `agent_onboarding.py:275-298` (plugins card → "Extend sase from the Admin Center", press `i` to install); visibility gated by `_apply_plugins_visibility` (`:162-167`, hidden when `plugins_installed`); source is third-party detection `discover_agents_onboarding_plugins_installed` → `any_plugins_installed()` (`actions/agents/_onboarding_plugins.py:8-10`, docstring "any local third-party SASE plugin"). CORRECT.
- (d) "Learn more" links into published docs: `changespec_onboarding.py:174-195` ("Learn more" card, `append_doc_link` to `sase.sh/change_spec/`, `/vcs/`, `/plugins/`); `axe_onboarding.py:210-231` ("Learn more" card); `agent_onboarding.py:301-327` (help card with doc links). CORRECT (agents card is titled "Get more help" rather than "Learn more", but carries the doc links).

**4. Agents header metric strip — IMPRECISE**
- Correct parts: no "Agents" word before the bracket (`agent_info_panel.py:308-309` appends `{visible_agent_count}` then the strip); zero-count metrics omitted (`:275` filters `if count`); leading N includes STARTING (`_display_detail.py:541-542` "`visible_agent_count` is the headline total that also includes hidden top-level STARTING rows"; `:464` `starting_count = len(hidden_starting_agents)`); startup renders `Agents: …` (`:303-307`).
- WRONG part: the enumerated format `N [S stopped · R running · W waiting · F failed · U unread · D done]` **omits the "starting" segment**. `_metric_counts()` (`agent_info_panel.py:263-272`) includes `("starting", starting)` between `asking`("stopped") and `running`, and it renders with a distinct highlighted style (`_COUNT_STYLES["starting"]`, `:285`). So the real strip is `N [<S> stopped · <G> starting · <R> running · <W> waiting · <F> failed · <U> unread · <D> done]`, with the `starting` segment appearing (when non-zero) between `stopped` and `running`. Correction: add the `· <N> starting` segment to the documented format.

**5. Models panel bindings — CORRECT**
- `src/sase/ace/tui/modals/models_panel.py:94-107` — `o`=override, `x`=clear, `e`=edit, `r`=reset, `escape`/`q`=close, nav `j`/`k`/`up`/`down`/`ctrl+n`/`ctrl+p`. Enter also triggers Override: `on_option_list_option_selected` → `action_override` (`:490-492`). `r` resets to implicit fallback via `action_reset` (`:319-340`, `ConfigEditOp.unset()`). All correct.

**6. Violet override pill text — CORRECT (with a caveat on "left")**
- `src/sase/ace/tui/widgets/alias_overrides_indicator.py:89` — one override: `f" Override @{alias} {remaining} "`; `:91` — several: `f" Overrides ×{len(overrides)} "`. The `×` is U+00D7 multiplication sign. CORRECT.
- Caveat: `remaining` from `format_remaining_until` (`llm_override_indicator.py:37-43`) has NO "left" word — it renders e.g. `25m`, `1h30m`, `2h`. So the literal pill is `Override @coder 25m` (not "25m left"). The `<time-left>` placeholder is fine as a description, but if the doc prints "25m left" that would be WRONG.

**7. Slow tool calls bullet — IMPRECISE**
- (a) Term: the UI/code section is titled **"SLOW TOOL CALLS"** (`_agent_slow_tools.py:90`), i.e. "tool calls", not "LLM tool calls". "LLM tool calls" is imprecise — should be "tool calls".
- (b) Threshold = 20s and there IS a max: `tools/_constants.py:14` `SLOW_TOOL_CALL_THRESHOLD_MS = 20_000`; `:15` `MAX_VISIBLE_SLOW_TOOL_CALLS = 8` (overflow shows "+N more · press ] for the full tools timeline", `_agent_slow_tools.py:98-103`). Selection uses `>=` threshold (`slow.py:109`) and displays "≥20s" (`_agent_slow_tools.py:80`), so "exceeding" is slightly loose (it's at-or-exceeding).
- (c) Ordered by start time ascending: CORRECT — `slow.py:63,112-114` sorts by `(started_at, line_number)`; `_agent_slow_tools.py:158-165` sorts by `(started_at, source_index, line_number)`.
- (d) Root aggregates across children with per-child attribution: CORRECT — `sources.py:116-149` `_build_root_sources` builds one source per agent-entry child with a child-derived `label` (`_source_label`, `:252-282`), and `_agent_slow_tools.py:193-216` renders a per-child source chip.
- (e) Where seen: appended to the agent metadata/details header (`_agent_display_header.py:413-421`, into `header_text` — the "agent metadata section", docstring `:99-102`). So "metadata header" is accurate — it's the selected agent's detail header section, not a separate panel.
- Net: mostly right, but "LLM tool calls" should be "tool calls", and it's worth noting the 20s threshold, the 8-item visible cap, and that selection is `>=` (at-or-exceeding).

**8. Leader `,?` rows on all three help tables + dispatch on AXE — CORRECT**
- Help-modal leader tables all include the `tab_guide` row: `help_modal/changespecs_bindings.py:169`, `help_modal/agents_bindings.py:119`, `help_modal/axe_bindings.py:67`.
- Dispatch is available on all three tabs including AXE (ungated tab_guide branch, `_leader_mode.py:71-75`).

**9. Action type spelled `LaunchApproval` — CORRECT**
- `src/sase/ace/tui/modals/notification_modal_actions.py:30` and `:48` — `notification.action in ("PlanApproval", "UserQuestion", "LaunchApproval")`; shared logic in `src/sase/launch_approval_actions.py`. Spelling `LaunchApproval` confirmed.

### Summary of items needing doc fixes
- **#4 (IMPRECISE):** add the missing `· <N> starting` segment (renders between `stopped` and `running` when the STARTING bucket is non-empty).
- **#7 (IMPRECISE):** "LLM tool calls" → "tool calls" (section header is "SLOW TOOL CALLS"); note threshold = 20s, max 8 visible rows (with "+N more"), and selection is at-or-exceeding (`>=`).
- **#6 (caveat):** the remaining-time has no "left" suffix (e.g. `Override @coder 25m`, not `25m left`).

I have verified all claims against the code. Here is my numbered verdict list.

## Verdicts

**1. CORRECT** — `src/sase/main/parser_update.py:61-66`. `-t/--to` has `choices=("dev", "pypi")` — exactly two, no `auto` or other choices. Flag help text (line 65): "Switch install mode to editable checkouts or published PyPI wheels".

**2. CORRECT** (all five parts).
- No-op on same mode: `src/sase/mode_switch/plan.py:83-95` returns a `changed=False` plan; `src/sase/main/update_handler.py:210-218` renders the no-op and returns 0.
- `-n/--dry-run` previews: `update_handler.py:220-225`.
- Confirmation required without `-y/--yes`, cancel exits non-zero: `update_handler.py:227-232` + `_confirm_mode_switch` (266-276); `_fail` returns 1 (478-492). Non-tty also returns False → exit 1.
- Changed switch restarts axe from CLI: `update_handler.py:244-262` via `restart_after_update`.
- ACE+axe from the Updates tab: `plugins_browser_mode_switch.py:196-204` → `_restart_after_update` → `plugins_browser_sase_update.py:468-471` `restart(restart_axe=True)` (restarts the TUI and axe).

**3. CORRECT** — `src/sase/mode_switch/plan.py:311-372` emits `git_clone` or `git_fetch`+`git_merge_ff` commands; `plan.py:238-248` builds the editable `uv_tool_install` reinstall set; `plan.py:250-258` adds the `rust_install_uv_tool` command (`just rust-install-uv-tool`, label "Rebuild sase-core-rs into the uv-tool venv"). `--to pypi`: `plan.py:295-299` builds a uv `build_reinstall_set` of published requirements. Minor nuance (not a defect): the Rust rebuild is conditional on `cargo`/core repo being present (`plan.py:169-201`); otherwise sase-core-rs stays on the PyPI wheel.

**4. CORRECT** — Owner-nested `<dev_root>/<owner>/<repo>`: `src/sase/mode_switch/repos.py:27-33` (`checkout_relpath` = `Path(owner)/checkout_name`) + `plan.py:386-387`. Config key `update.dev_root`, default `~/projects/github`: `repos.py:14,36-44` and `src/sase/default_config.yml:14` (`dev_root: "~/projects/github"`). SSH clone URLs: `repos.py:100-101` (`git@github.com:{full_name}.git`). Legacy flat `~/projects/git/<repo>` not reused + warns: `repos.py:15` (`LEGACY_FLAT_DEV_ROOT = "~/projects/git"`), `plan.py:390-402` (`_unused_flat_checkout_paths`), `plan.py:340-346` warns "existing checkout at {unused_path} is no longer used". (The warning fires only when the new owner-nested checkout does not already exist; the flat path is never used as a checkout target.)

**5. CORRECT** — `m` = "Switch mode" binding: `src/sase/ace/tui/modals/plugins_browser_pane.py:159`. Shows current mode + dev root: `plugins_browser_rendering.py:310-322` (renders `_install_mode`, and `· {dev_root}` when mode is dev). Confirm modal: `plugins_browser_mode_switch.py:126-157`. Background task: `plugins_browser_mode_switch.py:159-194` (`_submit_tracked_task`). Restart toast: `plugins_browser_mode_switch.py:196-204` (`write_pending_update_toast` + `_restart_after_update`).

**6. CORRECT** — CLI restart when uv changed packages: `src/sase/plugins/cli_restart.py:10-26` (`restart_after_plugin_change` → `_change_set_changed` → `restart_after_update`), used at `cli_install.py:135`, `cli_update.py:139`, `cli_uninstall.py:114`. Operation-specific ACE post-restart toasts: `plugins_browser_install.py:206`/`219` ("...successful install to load the new plugin"), `plugins_browser_update.py:302` ("...successful update to load the new plugin code"), `plugins_browser_uninstall.py:188` ("...successful uninstall to unload the plugin"). Same restart JSON shape as `sase update`: all use `restart_info_json` (`cli_install.py:269`, `cli_update.py:336`, `cli_uninstall.py:248`) — identical helper used by `sase update` in `src/sase/main/update_json.py:93,244`.

**7. CORRECT** — Matches code: on a package-set change the TUI install restarts ACE+axe and shows a post-restart toast, so entry points load immediately. `plugins_browser_install.py:277` ("Toast/restart after install; no-op installs refresh in place.") and the restart message at `206/219`; restart path is `restart(restart_axe=True)` via the shared `_restart_after_update` machinery.

**8. CORRECT** — `sase skill init -c/--check` exists with help "Report generated skill-file drift without writing files": `src/sase/main/parser_init.py:10-16` (`add_skills_init_arguments`), wired into `sase skill init` at `src/sase/main/parser_skills.py:40`. `sase init skills` alias: `parser_init.py:133-141` (help "Alias for `sase skill init`"). Scoped `--check` flags on memory/SDD/skills: `parser_init.py:97-103` (memory: "Report memory initialization drift without writing files"), `124-130` (sdd: "Report SDD config and generated-file drift without writing files"), and skills via `add_skills_init_arguments`. (`sase init` itself also has a top-level `--check` at 70-75, but each subcommand independently scopes its own.)

**9. CORRECT** — Help text: `src/sase/main/parser_bead.py:94-96` ("Maximum beads to print; closed listings default to 20, 0 means unlimited"). Empty open/in-progress + no explicit `--status` → falls back to closed: `src/sase/bead/cli_query.py:40-45`. Closed-in-scope + `--limit` omitted → 20: `cli_query.py:51-56` (`closed_in_scope = implicit_closed or Status.CLOSED in statuses`; `limit = DEFAULT_CLOSED_LIST_LIMIT` (=20, line 24); `issues = issues[-limit:]`). Sort: `src/sase/bead/db.py:335` `ORDER BY created_at ASC`, so `issues[-20:]` is the 20 **most-recently-created** (newest by `created_at`). `--limit 0` = unlimited: `nonnegative_int` allows 0 and `if limit:` (line 55) is falsy for 0 → no slicing, and the closed default only triggers when `limit is None`. Open/in-progress unlimited by default: `closed_in_scope` False → `limit` stays None → no cap. Cap DOES apply when scope mixes closed with open (e.g. `--status open --status closed`), because `Status.CLOSED in statuses` is True.

**10. CORRECT** — No `research*.md`/`research*.yml` under `src/sase/xprompts/` and no packaged-default registration for a `#research` xprompt anywhere in `src/sase`. Remaining "research" hits are unrelated: a docstring example in `src/sase/history/chat.py:52`, a var-name example in `xprompts/skills/sase_var.md:32-33`, and the SDD `research/` directory for tale/research files (`src/sase/sdd/_init_files.py:34-49`) — none is a packaged xprompt. So docs/sdd.md's "packaged default was removed" claim is accurate.

**11. CORRECT** — The keymap table describes the Updates tab (plugins browser) bindings. `src/sase/ace/tui/modals/plugins_browser_pane.py:154-171` BINDINGS include `i` (install, 157), `x` (uninstall, 158), `m` (switch_mode → "Switch mode", 159), `u` (update_sase, 160), `U` (update plugin, 161), `r` (refresh, 162) — so `m` belongs alongside `u/U/r/x/i`. The "PyPI managed ↔ dev editable; the `sase update --to` analog" description matches `action_switch_mode`, whose confirm variants run `("sase", "update", "--to", plan.target_mode)` (`plugins_browser_mode_switch.py:131`).

**12. CORRECT** — `src/sase/xprompt/model_completion.py`: `_LEADING_IMPLICIT_ALIASES` = `@default`, `@coder` (35-38); per-provider `@<provider>_coder` inserted in the middle via `coder_model_alias_for_provider` (204-211); `_TRAILING_IMPLICIT_ALIASES` = `@epic_creator`, `@epic_lander`, `@phase_worker` (39-43). Constant values confirmed in `src/sase/llm_provider/config.py:41,44,50,53,56` (`"default"`, `"coder"`, `"epic_creator"`, `"epic_lander"`, `"phase_worker"`); `_append_alias_entry` prefixes each with `@` (262). Exact set and ordering match the doc claim (also restated verbatim in the module docstring, lines 68-72).

All 12 claims are CORRECT as written. No corrections needed; the only worth-noting nuances are non-defects: claim 3's Rust rebuild is conditional on `cargo` availability, and claim 4/5's legacy-checkout warning and dev-root display are shown under the expected conditions (new checkout absent; dev mode active).

I have gathered all the evidence needed. Here are my verdicts.

## Verdict List

**1. IMPRECISE**

- `c` opens `ApproveOptionsModal`: CORRECT — `plan_approval_modal.py:99` (`("c", "custom", "Custom")`) → `action_custom` (`:289`) → `_push_approve_options` → `ApproveOptionsModal` (`:275-287`).
- "Also run:" section shown when family has custom roles: CORRECT — `approve_options_modal.py:220-227`.
- Checkbox glyphs `[x]`/`[ ]`: CORRECT — `approve_options_modal.py:264` (`marker = r"\[x]"` / `r"\[ ]"`).
- `after <role>` suffix: CORRECT but note it shows literal `custom` when the role has no `placement_after` — `approve_options_modal.py:266-268`.
- Digit-toggle range 1-9: CORRECT — `:328` (`event.key.isdigit() and event.key != "0"`), `:351-360`; members past index 9 render key `-` and cannot be digit-toggled (`:265`).
- **Row format is wrong two ways** (`_member_row_markup`, `approve_options_modal.py:270-272`): the actual string is `"{key} {marker} {display_label} {placement}"`, i.e. the **digit key is rendered FIRST**, before the checkbox — so the real row is `1 [x] <label> after <role>`, not `[x]/[ ] <label> after <role>`. And the `<label>` is **the role id humanized** (`role.id.replace("_", " ")`, `plan_approval_choices.py:341`), NOT the role's `label`/display-label field. So the answer to "display label or role id?" is: the role id.

**2. CORRECT**

- Role `default` merged with project config: `plan_approval_choices.py:336` (`default_enabled = default_overrides.get(role.id, role.default_enabled)`); project config source is `_configured_plan_approval_member_defaults` (`:500-528`), read from `agent_family.plan_approval.default_members`.
- Precedence explicit gate selection > project config > role definition default: explicit `selected_member_ids` overrides the merged defaults in the modal (`approve_options_modal.py:183-192`) and in `selected_member_ids_from_response_data` (`plan_approval_choices.py:434-456`, explicit response selection else request defaults); the merged default already places config over role default.

**3. CORRECT**

- `-w`/`--with`, `-W`/`--without`, both `action="append"` (repeatable): `parser_plan.py:86-103`.
- Same role in both → clear error "member option specified with both --with and --without: …": `plan_approval_choices.py:470-475`. Unknown role → "unknown plan-approval member option: …": `:540-543`.
- Both errors raised in `_selected_member_ids_for_cli` (`plan_approve_handler.py:118-129`, `132-171`) BEFORE `execute_plan_approval_response` writes `plan_response.json` (write happens at `plan_approval_actions.py:92-95`).

**4. IMPRECISE**

- Exists in `default_config.yml` with default `{}`: CORRECT — `default_config.yml:11` (`default_members: {}`).
- Schema mapping role id → boolean: CORRECT — `config/sase.schema.json:123-131`, `default_members` is `"type":"object"` with `"additionalProperties":{"type":"boolean"}` and `"default":{}`.
- "additionalProperties false at each level" is not accurate at the leaf: `additionalProperties:false` is set on the `agent_family` (`:116`) and `plan_approval` (`:121`) object levels only. The `default_members` level uses `additionalProperties:{"type":"boolean"}` (`:125-127`), NOT `false` — it must, to allow arbitrary role-id keys.

**5. CORRECT**

- Remote approvals carry no member toggles: `execute_mobile_plan_action` (`_mobile_notification_actions.py:32-108`) has no `selected_member_ids` parameter and never passes one to `execute_plan_approval_response`.
- Notification preview appends `Also run: <ids>`: `notifications/senders.py:271-277` (`notes.append(f"Also run: {', '.join(default_members)}")`).
- Sticky defaults apply remotely: the notification's `default_member_ids` come from the request payload built by `plan_approval_member_request_payload` (`plan_approval_choices.py:354-370`), which folds in config sticky defaults (`:324,:336`); with no explicit remote selection the runner falls back to `default_member_ids_from_request_data` via `selected_member_ids_from_response_data` (`:456`).

**6. CORRECT** (both sentences)

- "intersected with the default member ids" is accurate — it is auto:run **AND** default-on, not auto:run alone: `default_member_ids_from_request_data(..., auto_mode=True)` starts from the default ids then keeps only those with `auto == "run"` (`plan_approval_choices.py:427-431`).
- Auto plan approval limited to `approve`/`tale`/`epic`: `PLAN_APPROVAL_AUTO_MODE_CHOICES` derives from `auto_mode_eligible=True`, set only on approve (`:110`), tale (`:144`), epic (`:164`); legend is `False` (`:182`), run/commit unset. Confirmed by `PlanAutoApprovalAction = Literal["approve","epic","tale"]` (`plan_approve_handler.py:32`).

**7. CORRECT**

- Remote `run` archives into `sdd/tales/YYYYMM/`: `run` has `archive_side_effect=True`, `persist_action="approve"` (`plan_approval_choices.py:115-129`); `run_plan_side_effects` archives when `approval_choice_archives_plan` is true (`plan_approval_actions.py:220-221`); `_archive_plan_for_approval` maps `approve` persisted-action → `plan_kind="tales"` → `dest_dir = sdd_dir / "tales" / get_yyyymm()` (`:336-343`).
- It is labeled "Run": `display_label="Run"` (`:117`) and `run` is in `PLAN_APPROVAL_REMOTE_CHOICES` (`:237-244`).
- Interactive Approve archives to `sdd/tales/YYYYMM/`: same tales path; the TUI's own archiver writes `sdd_dir / _plan_kind_for_action(action) / get_yyyymm()` (`_notification_modals.py:377`), tales for approve.

**8. CORRECT** (applies to custom roles)

- Custom roles have `max_visits`, default 3: `validation.py:205-207` (`raw_role.get("max_visits", 3)`), field required on `AgentFamilyRoleDefinition` (`models.py:25`). (Built-in standard-chain roles have no such field; this cap is a custom-role feature.)
- Per-role visit count in family state incremented on re-review: `standard_plan_chain_evaluator.py:133,140-141` (`visit_counts[role.id] = prior_visits + 1`).
- At the cap the loop stops: `:134-139` (`prior_visits >= role.max_visits` → `cap_exhausted=True`); marked terminal with reason `custom_role_cap_exhausted` (`:200-203`).
- Terminates via finalize and records the exhausted role in artifacts: `run_agent_exec_plan_accept.py:385-392` writes `update_meta_field(..., "custom_role_cap_exhausted", transition.custom_role.role.id)` and returns the `"custom_role_cap_exhausted"` outcome.

**9. CORRECT**

- `label`/`done_label` replace status text on RUNNING/DONE: `agent.py:414-420` (`display_status`: RUNNING→`custom_role_label`, DONE→`custom_role_done_label`, else `status`).
- Presentation-only, semantic `status` unchanged: field comment `agent.py:272-274` ("never replace the semantic status string used for bucketing/actions").
- Labels come only from role definitions, not the launch site: populated by `apply_custom_role_display_labels` from persisted `agent_family_custom_role` metadata (`_meta_enrichment_common.py:183-195`; callers `_meta_enrichment_wire.py:76`, `_meta_enrichment_filesystem.py:102`); `label`/`done_label` originate on the role definition (`models.py:33-34`, `as_snapshot` `:52-53`, parsed in `validation.py:146-147,211,232`). There is no launch-site override path.

**10. CORRECT**

- Docs table: `docs/ace.md:1595-1606`. Every listed binding exists in `approve_options_modal.py`: Enter→approve (`:154`, on_key `:304`), a/t/e/l (`:156-159`, on_key `:312`), **m** select model (`:162`, on_key `:320`, `action_select_model` `:384`), **p** edit prompt (`:160`, on_key `:316`), 1-9 toggle (on_key `:328`), **Ctrl+N/Ctrl+P** next/prev (on_key `:332-339`, handled directly rather than via BINDINGS), q/Esc cancel (`:153,:163`).
- 1-9 toggling lives on THIS dialog (the `c`-opened `ApproveOptionsModal`), not the plain `PlanApprovalModal` — the latter's BINDINGS (`plan_approval_modal.py:95-109`) contain no digit keys and it has no digit `on_key` handling.

Now the docs/xprompt.md evaluator claim:

No manual ToC to update. Now validation — first check the justfile for docs/format targets:

Strict docs build passed and prettier normalized the tables. Now the repo-required `just check`:

All checks pass — format, lint, SASE validation, and the full test phase. Let me review the final diff of this session's edits:

All checks pass and the diff is clean. The changes are left uncommitted in the working tree.

# Review of the refresh-docs commit (`2b4d8e9ae`)

I verified every substantive claim in the commit against the current code using five parallel verification passes plus my own spot-checks of the family evaluator, attach path, and parsers. **Most of the commit is accurate** — the launch-approval surface (gating on `SASE_AGENT`, request schema, artifacts, modal keys, write-once responses), install-mode switching (`--to dev|pypi`, `dev_root`, owner-nested layout, restarts), plan-gate CLI/config/remote/`%auto`/archive behavior, beads `--limit` semantics, `skill init --check`, tab order, tab guide, Models panel, and all cross-doc anchors checked out. But it also contained several claims that don't match the system, which I fixed:

**Substantive corrections**

- **`%n` attach ≠ evaluator-inserted member** (docs/agent_families.md ×3, docs/xprompt.md). The docs claimed the family evaluator "treats an attached member identically to one it inserted itself" and that the two are "indistinguishable to the TUI." In reality a manual `%n(foo, tester)` runs outside the runner loop: it never emits `role_completed`, never gets the `agent_family_custom_role` snapshot, and therefore shows generic RUNNING/DONE instead of `TESTING`/`TESTED` labels (verified in `run_agent_exec.py`, `family_attach.py`, and the TUI meta-enrichment). All four passages now say what's actually shared (family metadata, grouping, dismissal) and what isn't (labels, templates, visit caps).
- **`on_done: re_review` doesn't route anything.** `on_done` is validated and snapshotted but has no runtime consumer; the re-review loop happens because the role's prompt template resubmits a plan, with the evaluator enforcing `max_visits`. The field table and Loop Caps section now describe it as declared intent plus template-driven looping.
- **Bundled examples**: the doc told users to copy the example YAML "together with its prompt-template xprompt" — the templates (`#agent_family_improve_plan`, `#agent_family_tester`) are already bundled and discoverable; only the `.yml` needs copying.
- **"Also run" row format** (ace.md + agent_families.md): rows actually render digit-first with the humanized role id, e.g. `1 [x] tester after code` — not `[x]/[ ] <label> after <role>`, and not the role's display `label`.
- **Agents info strip**: the documented format omitted the `starting` segment that renders between `stopped` and `running`; added it with a definition.
- **Slow tool calls**: "the agent's slowest LLM tool calls" → tool calls taking ≥ 20 seconds, capped at 8 rows with an overflow line pointing to the Tools panel.

**Clarity improvements for new users**

- Reworded the onboarding sentence so it's clear the Agents-tab launch walkthrough always shows and only the project/CL hint is gated on a launchable target.
- Clarified `%auto` member selection to "default-enabled **and** `auto: run`" (the "intersected with the default member ids" phrasing was correct but opaque).
- Promoted "Launch Approval" in ace.md from a subsection of "Plan Workflows" to its own section — it has nothing to do with plans.
- Small table fix: the `@` suffix row now says `@` in `%n` allocates the next number (it's never stored as a suffix itself).

**Checks run**: `just fmt-md` (prettier re-normalized the tables), `just docs-check` (strict MkDocs build passes), and the full `just check` — all gates green, including the test phase.

One thing I considered and skipped: reordering ace.md's per-tab keybinding sections to match the new Agents-first tab order. It would be a ~700-line move with "above/below" cross-reference churn for a reference doc readers navigate by ToC — not worth the diff noise, but easy to do later if you want it.

Worth flagging for engineering rather than docs: `on_done` currently has no runtime consumer at all, so `continue` vs `terminate` behave identically today — similar in spirit to the `@<provider>_coder` fallback gap flagged last session.

These are my changes from this session's documentation verification pass, so I'll commit them with the commit skill as instructed.

The status matches the three files I edited. Writing the commit message and committing:

Committed and pushed. Commit `9a784e2ca` — `docs: correct verified inaccuracies in agent families and ACE docs` — is on `master`, the working tree is clean, and the branch is in sync with `origin/master` (the commit workflow rebased onto the intervening `8585d194d` and pushed).

The commit contains exactly the three files from this session's verification pass (67 insertions, 58 deletions):

- **docs/agent_families.md / docs/xprompt.md** — corrected the claim that a manual `%n` attach is treated identically to an evaluator-inserted member (it runs outside the runner loop, never emits `role_completed`, and gets no custom-role display labels); reworded `on_done` as declared intent with template-driven re-review looping; noted that bundled prompt templates are already discoverable so only the example `.yml` needs copying; clarified the `@` suffix semantics.
- **docs/ace.md** — fixed the "Also run" row format (digit-first with humanized role id), added the missing `starting` segment to the agents info strip, tightened the slow-tool-calls description (≥ 20s threshold, 8-row cap), clarified onboarding launch-card gating, and promoted Launch Approval to its own section.

All gates were already green before the commit (`just fmt-md`, strict MkDocs build, full `just check`), and the pre-commit `just fix` hook ran again cleanly during the commit.
