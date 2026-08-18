# Chat History - ace-run (sase-p3.15.2--mon-1)

- **TIMESTAMP:** 2026-08-18 05:41:51 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-p3.15.2--mon-1

## Prompt

sase monitor start --command 'just check && just test-visual' --reason 'Re-verify plugin-config isolation after opting the LSP plugin-metadata test into real_plugin_config'

## Response

[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.28.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.27.18,<0.28.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
[setup] Installing required plugin sase-github from PyPI.
Resolved 1 package in 72ms
Checked 1 package in 0.05ms
[setup] Installing required plugin sase-research-artifacts from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-research-artifacts.
Resolved 1 package in 1ms
   Building sase-research-artifacts @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-research-artifacts
      Built sase-research-artifacts @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-research-artifacts
Prepared 1 package in 296ms
Uninstalled 1 package in 0.73ms
Installed 1 package in 1ms
 ~ sase-research-artifacts==0.1.0 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-research-artifacts)
✓ fmt (python)
✓ fmt (markdown)
✓ lint (keep-sorted)
✓ lint (ruff)
✓ lint (mypy)
✓ lint (feature flags)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (toobig)
✓ SASE validation
[core-floor-probe] stale_actionable: sase-core-rs==0.27.18 is missing 8 capability(s) that exist in a published sase-core release.
[core-floor-probe] bead_needs_task_type_migration: first appears in sase-core 85cc322 (feat(bead): add optional task_type to the issue wire and store); release v0.27.19 contains it.
[core-floor-probe] bead_task_type_migration_sql: first appears in sase-core 85cc322 (feat(bead): add optional task_type to the issue wire and store); release v0.27.19 contains it.
[core-floor-probe] parse_task_type_snapshot: first appears in sase-core 82b10b5 (feat(task_type): add spec validation, digest, and body rendering); release v0.27.20 contains it.
[core-floor-probe] render_task_type_body: first appears in sase-core 82b10b5 (feat(task_type): add spec validation, digest, and body rendering); release v0.27.20 contains it.
[core-floor-probe] serialize_task_type_snapshot: first appears in sase-core 82b10b5 (feat(task_type): add spec validation, digest, and body rendering); release v0.27.20 contains it.
[core-floor-probe] task_type_spec_digest: first appears in sase-core 82b10b5 (feat(task_type): add spec validation, digest, and body rendering); release v0.27.20 contains it.
[core-floor-probe] validate_task_type_field_values: first appears in sase-core 82b10b5 (feat(task_type): add spec validation, digest, and body rendering); release v0.27.20 contains it.
[core-floor-probe] validate_task_type_spec: first appears in sase-core 82b10b5 (feat(task_type): add spec validation, digest, and body rendering); release v0.27.20 contains it.
{"cache_hit": true, "capabilities": [{"commit": "85cc322", "name": "bead_needs_task_type_migration", "release": "v0.27.19", "subject": "feat(bead): add optional task_type to the issue wire and store"}, {"commit": "85cc322", "name": "bead_task_type_migration_sql", "release": "v0.27.19", "subject": "feat(bead): add optional task_type to the issue wire and store"}, {"commit": "82b10b5", "name": "parse_task_type_snapshot", "release": "v0.27.20", "subject": "feat(task_type): add spec validation, digest, and body rendering"}, {"commit": "82b10b5", "name": "render_task_type_body", "release": "v0.27.20", "subject": "feat(task_type): add spec validation, digest, and body rendering"}, {"commit": "82b10b5", "name": "serialize_task_type_snapshot", "release": "v0.27.20", "subject": "feat(task_type): add spec validation, digest, and body rendering"}, {"commit": "82b10b5", "name": "task_type_spec_digest", "release": "v0.27.20", "subject": "feat(task_type): add spec validation, digest, and body rendering"}, {"commit": "82b10b5", "name": "validate_task_type_field_values", "release": "v0.27.20", "subject": "feat(task_type): add spec validation, digest, and body rendering"}, {"commit": "82b10b5", "name": "validate_task_type_spec", "release": "v0.27.20", "subject": "feat(task_type): add spec validation, digest, and body rendering"}], "declared_floor": "0.27.18", "exit_code": 3, "message": "sase-core-rs==0.27.18 is missing 8 capability(s) that exist in a published sase-core release.", "status": "stale_actionable"}
✓ committed plans
✓ test (scoped)
scoped: escalated to the full suite (rules: root-conftest); contexts baseline not consulted
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.28.0 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.27.18,<0.28.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
[setup] Installing required plugin sase-github from PyPI.
Resolved 1 package in 63ms
Checked 1 package in 0.05ms
[setup] Installing required plugin sase-research-artifacts from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-research-artifacts.
Resolved 1 package in 2ms
   Building sase-research-artifacts @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-research-artifacts
      Built sase-research-artifacts @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-research-artifacts
Prepared 1 package in 297ms
Uninstalled 1 package in 0.96ms
Installed 1 package in 1ms
 ~ sase-research-artifacts==0.1.0 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/linked/sase-research-artifacts)

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-visual              │
└───────────────────────────────────────────────────────┘

---------- Running visual pytest subset... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.3, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, hypothesis-6.165.3, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [712 items]

........................................................................ [ 10%]
........................................................................ [ 20%]
........................................................................ [ 30%]
........................................................................ [ 40%]
........................................................................ [ 50%]
........................................................................ [ 60%]
........................................................................ [ 70%]
........................................................................ [ 80%]
.....F..................F............................................... [ 91%]
................................................................         [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=================================== FAILURES ===================================
______________ test_real_fakey_completed_retry_chain_png_snapshot ______________
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

prompt = 'Exercise the retry pipeline.'
agent_type = 'workflow-tmp_260818_053919-main', model_tier = 'large'
model_size = None, iteration = None, workflow_tag = None
artifacts_dir = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-53/popen-gw0/test_real_fakey_completed_retr0/sase-home/projects/fakey-e2e/artifacts/ace-run/20260706114500'
workflow = 'tmp_260818_053919', suppress_output = False, timestamp = None
is_home_mode = False, branch_or_workspace = 'fakey-e2e', decision_counts = None
provider_name = 'fakey', skip_preprocessing = True
directives = PromptDirectives(auto_mode=None, auto_enabled=False, auto_argument=None, hide=False, model='fakey-large', model_alias=...t=None, tribe=None, wait=[], wait_beads=[], wait_duration=None, wait_until=None, wait_runners=None, wait_priority=None)
launch_selection = LaunchSelection(provider='fakey', model='fakey-large', reasoning_effort=None, effort_explicit=False, alias_trail=(), alias_origin='none')

    def invoke_agent(
        prompt: str,
        *,
        agent_type: str,
        model_tier: ModelTier = "large",
        model_size: Literal["little", "big"] | None = None,
        iteration: int | None = None,
        workflow_tag: str | None = None,
        artifacts_dir: str | None = None,
        workflow: str | None = None,
        suppress_output: bool = False,
        timestamp: str | None = None,
        is_home_mode: bool = False,
        branch_or_workspace: str | None = None,
        decision_counts: dict[str, Any] | None = None,
        provider_name: str | None = None,
        skip_preprocessing: bool = False,
        directives: PromptDirectives | None = None,
        launch_selection: LaunchSelection | None = None,
    ) -> AIMessage:
        """Invoke an LLM agent with standard preprocessing, logging, and postprocessing.
    
        This is the main entry point for sending prompts to any configured LLM
        backend. It handles the full lifecycle:
    
        1. Preprocess the prompt (xprompt, file refs, jinja2, prettier).
        2. Display decision counts and prompt (if not suppressed).
        3. Save prompt to artifacts directory.
        4. Get provider from registry and invoke.
        5. Postprocess response (logging, chat history, audio).
        6. Return AIMessage.
    
        Args:
            prompt: The raw prompt to send to the agent.
            agent_type: Type of agent (e.g., "editor", "planner", "research").
            model_tier: Model tier ("large" or "small").
            model_size: Deprecated. Use ``model_tier`` instead. Maps "big" to
                "large" and "little" to "small".
            iteration: Optional iteration number.
            workflow_tag: Optional workflow tag.
            artifacts_dir: Optional artifacts directory for logging.
            workflow: Optional workflow name for chat history.
            suppress_output: If True, suppress output display.
            timestamp: Optional timestamp for chat file naming (YYmmdd_HHMMSS).
            is_home_mode: If True, skip file copying for ``@`` file references.
            branch_or_workspace: Optional branch/workspace name for chat history
                filenames. When not provided, auto-detected from the current
                working directory.
            decision_counts: Optional planning agent decision counts for display.
            provider_name: Optional provider name override (default from config).
            skip_preprocessing: If True, skip the ``preprocess_prompt()`` call
                and use the prompt as-is (caller already preprocessed).
            directives: Pre-extracted prompt directives to use when
                ``skip_preprocessing=True``.
            launch_selection: An already-resolved provider/model/effort
                selection. When supplied, ``invoke_agent()`` uses it as-is
                instead of resolving *directives* itself, so a caller that
                already consumed a pooled model alias (e.g. the workflow
                executor's prompt step) does not advance its cursor twice.
    
        Returns:
            The AIMessage response from the agent.
        """
        # Handle deprecated model_size parameter
        if model_size is not None:
            model_tier = _MODEL_SIZE_TO_TIER[model_size]
    
        # Check for global model tier override (env var)
        tier_override = os.environ.get("SASE_MODEL_TIER_OVERRIDE") or os.environ.get(
            "SASE_MODEL_SIZE_OVERRIDE"
        )
        if tier_override:
            # Accept both old ("big"/"little") and new ("large"/"small") values
            if tier_override in _MODEL_SIZE_TO_TIER:
                model_tier = _MODEL_SIZE_TO_TIER[tier_override]
            elif tier_override in ("large", "small"):
                model_tier = cast(ModelTier, tier_override)
    
        # Build logging context
        context = LoggingContext(
            agent_type=agent_type,
            iteration=iteration,
            workflow_tag=workflow_tag,
            artifacts_dir=artifacts_dir,
            suppress_output=suppress_output,
            workflow=workflow,
            timestamp=timestamp,
            is_home_mode=is_home_mode,
            branch_or_workspace=branch_or_workspace,
            decision_counts=decision_counts,
        )
    
        # 1. Preprocess prompt
        if skip_preprocessing:
            query = prompt
            result_directives = directives or PromptDirectives()
        else:
            result = preprocess_prompt(prompt, is_home_mode=is_home_mode)
            query = result.prompt
            result_directives = result.directives
        model_override = result_directives.model
        model_alias_overrides = dict(result_directives.model_alias_overrides)
        if model_alias_overrides and artifacts_dir:
            from .launch_alias_overrides import export_launch_alias_overrides
    
            export_launch_alias_overrides(model_alias_overrides)
            from sase.axe.run_agent_helpers import update_meta_field
    
            update_meta_field(
                artifacts_dir,
                "model_alias_overrides",
                model_alias_overrides,
            )
    
        # A caller that already consumed a pooled model alias (e.g. the workflow
        # executor's prompt step, immediately before this call) hands over that
        # exact selection so it is never resolved — and never consumed — twice.
        provider_disables = capture_provider_disable_snapshot() or None
        if launch_selection is not None:
            provider_name = launch_selection.provider
            model_override = launch_selection.model
            effective_effort = launch_selection.reasoning_effort
            effort_explicit = launch_selection.effort_explicit
        else:
            from .launch_selection import resolve_launch_selection
    
            if provider_disables is None:
                selection = resolve_launch_selection(
                    result_directives,
                    model_alias_overrides,
                    model_tier=model_tier,
                    provider_name=provider_name,
                    consume=True,
                )
            else:
                selection = resolve_launch_selection(
                    result_directives,
                    model_alias_overrides,
                    model_tier=model_tier,
                    provider_name=provider_name,
                    consume=True,
                    provider_disables=provider_disables,
                )
            if selection is not None:
                provider_name = selection.provider
                model_override = selection.model
                effective_effort = selection.reasoning_effort
                effort_explicit = selection.effort_explicit
            else:
                # Caller supplied provider_name directly with no %model directive;
                # nothing to resolve here (model_tier drives the fallback below).
                effective_effort, effort_explicit = resolve_effective_effort(
                    result_directives, None
                )
    
        invocation_options = LLMInvocationOptions(
            reasoning_effort=effective_effort,
            explicit=effort_explicit,
        )
    
        # 2. Build display label
        if model_override:
            agent_type_with_tier = f"{agent_type} [{model_override}]"
        else:
            model_tier_label = _MODEL_TIER_TO_LABEL[model_tier]
            agent_type_with_tier = f"{agent_type} [{model_tier_label}]"
    
        # 3. Display decision counts (if not suppressed)
        if not suppress_output and decision_counts is not None:
            print_decision_counts(decision_counts)
    
        # 4. Print prompt BEFORE execution (if not suppressed)
        if not suppress_output:
            print_prompt_and_response(
                prompt=query,
                response="",
                agent_type=agent_type_with_tier,
                iteration=iteration,
                show_prompt=True,
                show_response=False,
            )
    
        # 5. Generate or use provided timestamp
        start_timestamp = timestamp or generate_timestamp()
    
        # 6. Save prompt to artifacts
        if artifacts_dir:
            save_prompt_to_file(
                prompt=query,
                artifacts_dir=artifacts_dir,
                agent_type=agent_type,
                iteration=iteration,
            )
    
        # 7. Get provider and invoke
        if provider_name:
            requested_provider_label = provider_name
        elif provider_disables is None:
            requested_provider_label = get_default_provider_name()
        else:
            requested_provider_label = get_default_provider_name(
                provider_disables=provider_disables
            )
        if provider_disables is None:
            execution_provider_label = resolve_execution_provider_name(
                requested_provider_label
            )
        else:
            execution_provider_label = resolve_execution_provider_name(
                requested_provider_label,
                provider_disables=provider_disables,
            )
        execution_override_active = bool(os.environ.get(LLM_EXEC_PROVIDER_ENV, "").strip())
        provider_lookup_name = (
            execution_provider_label if execution_override_active else provider_name
        )
        context.metadata_llm_provider = requested_provider_label
        context.metadata_model = model_override
        t0 = time.monotonic()
        try:
            if provider_disables is None:
                provider = get_provider(provider_lookup_name)
            else:
                provider = get_provider(
                    provider_lookup_name,
                    provider_disables=provider_disables,
                )
            if artifacts_dir:
                from sase.axe.run_agent_helpers import update_meta_field
    
                update_meta_field(
                    artifacts_dir,
                    "exec_llm_provider",
                    execution_provider_label,
                )
            if context.metadata_model is None:
                metadata_provider = provider
                if execution_provider_label != requested_provider_label:
                    if provider_disables is None:
                        metadata_provider = get_provider(requested_provider_label)
                    else:
                        metadata_provider = get_provider(
                            requested_provider_label,
                            provider_disables=provider_disables,
                        )
                resolved_model = metadata_provider.resolve_model_name(model_tier)
                if resolved_model and resolved_model != "unknown":
                    context.metadata_model = resolved_model
>           invoke_result = provider.invoke(
                query,
                model_tier=model_tier,
                suppress_output=suppress_output,
                model_override=model_override,
                options=invocation_options,
            )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/_invoke.py:303: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/_plugin_manager.py:31: in invoke
    result = self._pm.hook.llm_invoke(
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/fakey.py:194: in llm_invoke
    return self.invoke(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <sase.llm_provider.fakey.FakeyProvider object at 0x7fb80760ecf0>
prompt = 'Exercise the retry pipeline.', model_tier = 'large'
suppress_output = False, model_override = 'fakey-large'
options = LLMInvocationOptions(reasoning_effort=None, explicit=False)

    def invoke(
        self,
        prompt: str,
        *,
        model_tier: ModelTier,
        suppress_output: bool = False,
        model_override: str | None = None,
        options: LLMInvocationOptions | None = None,
    ) -> InvokeResult:
        model = model_override or _TIER_TO_MODEL[model_tier]
        base_args = [_fakey_bin(), "--model", model]
        base_args.extend(self.invocation_option_args(options))
    
        if model_tier == "large":
            extra_args = os.environ.get(
                "SASE_LLM_LARGE_ARGS", os.environ.get("SASE_FAKEY_LARGE_ARGS")
            )
        else:
            extra_args = os.environ.get(
                "SASE_LLM_SMALL_ARGS", os.environ.get("SASE_FAKEY_SMALL_ARGS")
            )
        if extra_args:
            base_args.extend(extra_args.split())
    
        timer_context = (
            provider_timer("Waiting for Fakey") if not suppress_output else None
        )
        current_prompt = prompt
        accumulated_response = ""
        total_usage: dict[str, int] | None = None
        cycle = 0
    
        while True:
            if timer_context:
                with timer_context:
                    content, stderr_content, return_code = self._run_subprocess(
                        base_args, current_prompt, suppress_output
                    )
                    print()
            else:
                content, stderr_content, return_code = self._run_subprocess(
                    base_args, current_prompt, suppress_output
                )
    
            content, usage = _extract_usage(content)
            if usage is not None:
                if total_usage is None:
                    total_usage = {}
                for key, value in usage.items():
                    total_usage[key] = total_usage.get(key, 0) + value
    
            if self._pending_interrupt_message is not None:
                user_msg = self._pending_interrupt_message
                self._pending_interrupt_message = None
                cycle += 1
                _log_interrupt(user_msg, cycle)
                accumulated_response = (
                    accumulated_response + "\n\n" + content.strip()
                ).strip()
                current_prompt = (
                    f"{prompt}\n\n"
                    f"--- Work So Far ---\n{accumulated_response}\n\n"
                    f"--- User Message ---\n{user_msg}\n\n"
                    "Continue working, incorporating the user's message above."
                )
                continue
    
            if return_code != 0:
>               raise subprocess.CalledProcessError(
                    return_code,
                    base_args,
                    output=content,
                    stderr=stderr_content,
                )
E               subprocess.CalledProcessError: Command '['/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/fakey', '--model', 'fakey-large']' returned non-zero exit status 1.

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/fakey.py:270: CalledProcessError

The above exception was the direct cause of the following exception:

self = <sase.xprompt.workflow_executor.WorkflowExecutor object at 0x7fb7de723530>

    def execute(self) -> bool:
        """Execute all workflow steps sequentially.
    
        Steps marked with ``finally_=True`` run even when a prior step has
        failed.  Non-finally steps are skipped after a failure.  If no
        ``finally`` steps exist the behavior is identical to before.
    
        Returns:
            True if workflow completed successfully, False otherwise.
        """
        self._save_state()
    
        # Inject workflow environment variables before any steps run
        if self.workflow.environment:
            self._inject_environment()
    
        total_steps = len(self.workflow.steps)
        has_finally_steps = any(s.finally_ for s in self.workflow.steps)
    
        # Notify workflow start
        if self.output_handler:
            self.output_handler.on_workflow_start(
                self.workflow.name,
                dict(self.context),
                total_steps,
            )
    
        # Track failure info so finally steps can still run
        failure_exception: WorkflowExecutionError | None = None
        failure_returned_false: bool = False
    
        for i, step in enumerate(self.workflow.steps):
            self.state.current_step_index = i
            step_state = self.state.steps[i]
            step_start_time = time.time()
    
            # Determine step type for display
            step_type = self._get_step_type(step)
    
            # After a failure, skip non-finally steps
            hit_failure = failure_exception is not None or failure_returned_false
            if hit_failure and not step.finally_:
                step_state.status = StepStatus.SKIPPED
                self.context[step.name] = {}
                self._save_state()
                if self.output_handler:
                    self.output_handler.on_step_start(
                        step.name, step_type, i, total_steps
                    )
                    self.output_handler.on_step_skip(
                        step.name, reason="prior step failed"
                    )
                continue
    
            # Check if step should be skipped due to provided step input
            if step.name in self._step_inputs:
                step_state.status = StepStatus.SKIPPED
                step_state.output = self._step_inputs[step.name]
                self.context[step.name] = self._step_inputs[step.name]
                self._save_state()
                if self.output_handler:
                    self.output_handler.on_step_start(
                        step.name,
                        step_type,
                        i,
                        total_steps,
                    )
                    self.output_handler.on_step_skip(
                        step.name, reason="step input provided"
                    )
                continue
    
            # Evaluate if: condition
            condition_result: bool | None = None
            if step.condition:
                condition_result = self._evaluate_condition(step.condition)
                if not condition_result:
                    step_state.status = StepStatus.SKIPPED
                    self.context[step.name] = {}
                    self._save_state()
                    # Notify step skipped
                    if self.output_handler:
                        self.output_handler.on_step_start(
                            step.name,
                            step_type,
                            i,
                            total_steps,
                            condition=step.condition,
                            condition_result=condition_result,
                        )
                        self.output_handler.on_step_skip(
                            step.name, reason="condition false"
                        )
                    continue
    
            step_state.status = StepStatus.IN_PROGRESS
            self._save_state()
    
            # Save initial "running" marker with step index for TUI display
            self._save_prompt_step_marker(
                step.name,
                step_state,
                step_type,
                step_index=i,
                hidden=step.hidden,
                output_types=self._get_output_types(i),
            )
    
            # Notify step start
            if self.output_handler:
                loop_info = self._get_loop_info(step)
                self.output_handler.on_step_start(
                    step.name,
                    step_type,
                    i,
                    total_steps,
                    condition=step.condition,
                    condition_result=condition_result,
                    loop_info=loop_info,
                )
    
            self._last_for_zero_iterations = False
    
            try:
                # Handle control flow constructs
                if step.for_loop and step.parallel_config:
                    success = self._execute_for_parallel_step(step, step_state)
                elif step.for_loop:
                    success = self._execute_for_step(step, step_state)
                elif step.repeat_config:
                    success = self._execute_repeat_step(step, step_state)
                elif step.while_config:
                    success = self._execute_while_step(step, step_state)
                elif step.parallel_config:
                    success = self._execute_parallel_step(step, step_state)
                elif step.is_agent_step():
>                   success = self._execute_prompt_step(step, step_state)
                              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/xprompt/workflow_executor.py:330: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/xprompt/workflow_executor_steps_prompt.py:383: in _execute_prompt_step
    response = invoke_agent(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

prompt = 'Exercise the retry pipeline.'
agent_type = 'workflow-tmp_260818_053919-main', model_tier = 'large'
model_size = None, iteration = None, workflow_tag = None
artifacts_dir = '/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-53/popen-gw0/test_real_fakey_completed_retr0/sase-home/projects/fakey-e2e/artifacts/ace-run/20260706114500'
workflow = 'tmp_260818_053919', suppress_output = False, timestamp = None
is_home_mode = False, branch_or_workspace = 'fakey-e2e', decision_counts = None
provider_name = 'fakey', skip_preprocessing = True
directives = PromptDirectives(auto_mode=None, auto_enabled=False, auto_argument=None, hide=False, model='fakey-large', model_alias=...t=None, tribe=None, wait=[], wait_beads=[], wait_duration=None, wait_until=None, wait_runners=None, wait_priority=None)
launch_selection = LaunchSelection(provider='fakey', model='fakey-large', reasoning_effort=None, effort_explicit=False, alias_trail=(), alias_origin='none')

    def invoke_agent(
        prompt: str,
        *,
        agent_type: str,
        model_tier: ModelTier = "large",
        model_size: Literal["little", "big"] | None = None,
        iteration: int | None = None,
        workflow_tag: str | None = None,
        artifacts_dir: str | None = None,
        workflow: str | None = None,
        suppress_output: bool = False,
        timestamp: str | None = None,
        is_home_mode: bool = False,
        branch_or_workspace: str | None = None,
        decision_counts: dict[str, Any] | None = None,
        provider_name: str | None = None,
        skip_preprocessing: bool = False,
        directives: PromptDirectives | None = None,
        launch_selection: LaunchSelection | None = None,
    ) -> AIMessage:
        """Invoke an LLM agent with standard preprocessing, logging, and postprocessing.
    
        This is the main entry point for sending prompts to any configured LLM
        backend. It handles the full lifecycle:
    
        1. Preprocess the prompt (xprompt, file refs, jinja2, prettier).
        2. Display decision counts and prompt (if not suppressed).
        3. Save prompt to artifacts directory.
        4. Get provider from registry and invoke.
        5. Postprocess response (logging, chat history, audio).
        6. Return AIMessage.
    
        Args:
            prompt: The raw prompt to send to the agent.
            agent_type: Type of agent (e.g., "editor", "planner", "research").
            model_tier: Model tier ("large" or "small").
            model_size: Deprecated. Use ``model_tier`` instead. Maps "big" to
                "large" and "little" to "small".
            iteration: Optional iteration number.
            workflow_tag: Optional workflow tag.
            artifacts_dir: Optional artifacts directory for logging.
            workflow: Optional workflow name for chat history.
            suppress_output: If True, suppress output display.
            timestamp: Optional timestamp for chat file naming (YYmmdd_HHMMSS).
            is_home_mode: If True, skip file copying for ``@`` file references.
            branch_or_workspace: Optional branch/workspace name for chat history
                filenames. When not provided, auto-detected from the current
                working directory.
            decision_counts: Optional planning agent decision counts for display.
            provider_name: Optional provider name override (default from config).
            skip_preprocessing: If True, skip the ``preprocess_prompt()`` call
                and use the prompt as-is (caller already preprocessed).
            directives: Pre-extracted prompt directives to use when
                ``skip_preprocessing=True``.
            launch_selection: An already-resolved provider/model/effort
                selection. When supplied, ``invoke_agent()`` uses it as-is
                instead of resolving *directives* itself, so a caller that
                already consumed a pooled model alias (e.g. the workflow
                executor's prompt step) does not advance its cursor twice.
    
        Returns:
            The AIMessage response from the agent.
        """
        # Handle deprecated model_size parameter
        if model_size is not None:
            model_tier = _MODEL_SIZE_TO_TIER[model_size]
    
        # Check for global model tier override (env var)
        tier_override = os.environ.get("SASE_MODEL_TIER_OVERRIDE") or os.environ.get(
            "SASE_MODEL_SIZE_OVERRIDE"
        )
        if tier_override:
            # Accept both old ("big"/"little") and new ("large"/"small") values
            if tier_override in _MODEL_SIZE_TO_TIER:
                model_tier = _MODEL_SIZE_TO_TIER[tier_override]
            elif tier_override in ("large", "small"):
                model_tier = cast(ModelTier, tier_override)
    
        # Build logging context
        context = LoggingContext(
            agent_type=agent_type,
            iteration=iteration,
            workflow_tag=workflow_tag,
            artifacts_dir=artifacts_dir,
            suppress_output=suppress_output,
            workflow=workflow,
            timestamp=timestamp,
            is_home_mode=is_home_mode,
            branch_or_workspace=branch_or_workspace,
            decision_counts=decision_counts,
        )
    
        # 1. Preprocess prompt
        if skip_preprocessing:
            query = prompt
            result_directives = directives or PromptDirectives()
        else:
            result = preprocess_prompt(prompt, is_home_mode=is_home_mode)
            query = result.prompt
            result_directives = result.directives
        model_override = result_directives.model
        model_alias_overrides = dict(result_directives.model_alias_overrides)
        if model_alias_overrides and artifacts_dir:
            from .launch_alias_overrides import export_launch_alias_overrides
    
            export_launch_alias_overrides(model_alias_overrides)
            from sase.axe.run_agent_helpers import update_meta_field
    
            update_meta_field(
                artifacts_dir,
                "model_alias_overrides",
                model_alias_overrides,
            )
    
        # A caller that already consumed a pooled model alias (e.g. the workflow
        # executor's prompt step, immediately before this call) hands over that
        # exact selection so it is never resolved — and never consumed — twice.
        provider_disables = capture_provider_disable_snapshot() or None
        if launch_selection is not None:
            provider_name = launch_selection.provider
            model_override = launch_selection.model
            effective_effort = launch_selection.reasoning_effort
            effort_explicit = launch_selection.effort_explicit
        else:
            from .launch_selection import resolve_launch_selection
    
            if provider_disables is None:
                selection = resolve_launch_selection(
                    result_directives,
                    model_alias_overrides,
                    model_tier=model_tier,
                    provider_name=provider_name,
                    consume=True,
                )
            else:
                selection = resolve_launch_selection(
                    result_directives,
                    model_alias_overrides,
                    model_tier=model_tier,
                    provider_name=provider_name,
                    consume=True,
                    provider_disables=provider_disables,
                )
            if selection is not None:
                provider_name = selection.provider
                model_override = selection.model
                effective_effort = selection.reasoning_effort
                effort_explicit = selection.effort_explicit
            else:
                # Caller supplied provider_name directly with no %model directive;
                # nothing to resolve here (model_tier drives the fallback below).
                effective_effort, effort_explicit = resolve_effective_effort(
                    result_directives, None
                )
    
        invocation_options = LLMInvocationOptions(
            reasoning_effort=effective_effort,
            explicit=effort_explicit,
        )
    
        # 2. Build display label
        if model_override:
            agent_type_with_tier = f"{agent_type} [{model_override}]"
        else:
            model_tier_label = _MODEL_TIER_TO_LABEL[model_tier]
            agent_type_with_tier = f"{agent_type} [{model_tier_label}]"
    
        # 3. Display decision counts (if not suppressed)
        if not suppress_output and decision_counts is not None:
            print_decision_counts(decision_counts)
    
        # 4. Print prompt BEFORE execution (if not suppressed)
        if not suppress_output:
            print_prompt_and_response(
                prompt=query,
                response="",
                agent_type=agent_type_with_tier,
                iteration=iteration,
                show_prompt=True,
                show_response=False,
            )
    
        # 5. Generate or use provided timestamp
        start_timestamp = timestamp or generate_timestamp()
    
        # 6. Save prompt to artifacts
        if artifacts_dir:
            save_prompt_to_file(
                prompt=query,
                artifacts_dir=artifacts_dir,
                agent_type=agent_type,
                iteration=iteration,
            )
    
        # 7. Get provider and invoke
        if provider_name:
            requested_provider_label = provider_name
        elif provider_disables is None:
            requested_provider_label = get_default_provider_name()
        else:
            requested_provider_label = get_default_provider_name(
                provider_disables=provider_disables
            )
        if provider_disables is None:
            execution_provider_label = resolve_execution_provider_name(
                requested_provider_label
            )
        else:
            execution_provider_label = resolve_execution_provider_name(
                requested_provider_label,
                provider_disables=provider_disables,
            )
        execution_override_active = bool(os.environ.get(LLM_EXEC_PROVIDER_ENV, "").strip())
        provider_lookup_name = (
            execution_provider_label if execution_override_active else provider_name
        )
        context.metadata_llm_provider = requested_provider_label
        context.metadata_model = model_override
        t0 = time.monotonic()
        try:
            if provider_disables is None:
                provider = get_provider(provider_lookup_name)
            else:
                provider = get_provider(
                    provider_lookup_name,
                    provider_disables=provider_disables,
                )
            if artifacts_dir:
                from sase.axe.run_agent_helpers import update_meta_field
    
                update_meta_field(
                    artifacts_dir,
                    "exec_llm_provider",
                    execution_provider_label,
                )
            if context.metadata_model is None:
                metadata_provider = provider
                if execution_provider_label != requested_provider_label:
                    if provider_disables is None:
                        metadata_provider = get_provider(requested_provider_label)
                    else:
                        metadata_provider = get_provider(
                            requested_provider_label,
                            provider_disables=provider_disables,
                        )
                resolved_model = metadata_provider.resolve_model_name(model_tier)
                if resolved_model and resolved_model != "unknown":
                    context.metadata_model = resolved_model
            invoke_result = provider.invoke(
                query,
                model_tier=model_tier,
                suppress_output=suppress_output,
                model_override=model_override,
                options=invocation_options,
            )
            invoke_result = run_commit_finalizer(
                provider=provider,
                original_prompt=query,
                invoke_result=invoke_result,
                model_tier=model_tier,
                suppress_output=suppress_output,
                model_override=model_override,
                artifacts_dir=artifacts_dir,
                options=invocation_options,
            )
            response_content = invoke_result.content
    
            # Record success metrics
            elapsed = time.monotonic() - t0
            LLM_INVOCATIONS.labels(provider=execution_provider_label, status="ok").inc()
            LLM_INVOCATION_DURATION.labels(provider=execution_provider_label).observe(
                elapsed
            )
            if invoke_result.usage:
                LLM_INPUT_TOKENS.labels(provider=execution_provider_label).inc(
                    invoke_result.usage.get("input_tokens", 0)
                )
                LLM_OUTPUT_TOKENS.labels(provider=execution_provider_label).inc(
                    invoke_result.usage.get("output_tokens", 0)
                )
                LLM_CACHE_READ_TOKENS.labels(provider=execution_provider_label).inc(
                    invoke_result.usage.get("cache_read_input_tokens", 0)
                )
    
            # 8. Postprocess success
            postprocess_success(
                prompt=query,
                response=response_content,
                context=context,
                model_tier=model_tier,
                start_timestamp=start_timestamp,
            )
    
            return AIMessage(content=response_content)
    
        except subprocess.CalledProcessError as e:
            elapsed = time.monotonic() - t0
            LLM_INVOCATIONS.labels(provider=execution_provider_label, status="error").inc()
            LLM_INVOCATION_DURATION.labels(provider=execution_provider_label).observe(
                elapsed
            )
            LLM_ERRORS.labels(
                provider=execution_provider_label, error_type="CalledProcessError"
            ).inc()
    
            parts = [f"Error running LLM provider command (exit code {e.returncode})"]
            if e.stderr:
                parts.append(f"stderr: {e.stderr.strip()}")
            if e.output:
                parts.append(f"output: {e.output.strip()}")
            error_content = "\n".join(parts)
    
            handle_possible_usage_limit(
                provider=execution_provider_label,
                error_text=error_content,
                model=context.metadata_model,
                artifacts_dir=artifacts_dir,
            )
    
            postprocess_error(
                prompt=query,
                error_content=error_content,
                context=context,
                model_tier=model_tier,
                start_timestamp=start_timestamp,
            )
    
>           raise LLMInvocationError(error_content) from e
E           sase.llm_provider.types.LLMInvocationError: Error running LLM provider command (exit code 1)
E           stderr: FAKEY-RETRYABLE: temporarily unavailable

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/llm_provider/_invoke.py:382: LLMInvocationError

The above exception was the direct cause of the following exception:

ctx = AgentExecContext(cl_name='fakey-e2e', project_file='/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-53/popen-gw0/test_re...en=False, agent_meta={}, local_xprompts={}, multi_agent_prompt_file=None, wait_chats=[], output_variable_namespaces={})
prompt = '%model:fakey-large\nExercise the retry pipeline.'

    def run_execution_loop(
        ctx: AgentExecContext,
        prompt: str,
    ) -> _AgentExecResult:
        """Run the agent workflow loop with retry, plan approval, and question handling."""
        from sase.xprompt.models import create_anonymous_workflow
        from sase.xprompt.workflow_runner import execute_workflow
    
        _publish_predicted_chat_path(ctx)
        _publish_root_timestamp(ctx)
    
        from sase.llm_provider.registry import (
            LLM_EXEC_PROVIDER_ENV,
            resolve_execution_provider_name,
        )
    
        has_execution_provider = bool(
            ctx.agent_llm_provider or os.environ.get(LLM_EXEC_PROVIDER_ENV, "").strip()
        )
        execution_provider = (
            resolve_execution_provider_name(ctx.agent_llm_provider)
            if has_execution_provider
            else None
        )
        tracker = RetryTracker(
            retry_cfg=(
                get_retry_config(execution_provider)
                if execution_provider is not None
                else None
            ),
            attempt_start_epoch=time.time(),
            execution_provider=execution_provider,
        )
        state = LoopState(
            current_prompt=prompt,
            current_role_suffix="",
            current_artifacts_dir=ctx.artifacts_dir,
            loop_outcome="completed",
            sdd_spec_path=None,
            original_prompt=prompt,
            original_agent_timestamp=os.environ.get("SASE_AGENT_TIMESTAMP"),
        )
        result = None
    
        while True:
            reset_killed()
            _publish_phase_env(state.current_artifacts_dir)
            anon_workflow = create_anonymous_workflow(state.current_prompt)
            if ctx.local_xprompts:
                anon_workflow.xprompts = ctx.local_xprompts
    
            try:
>               result = execute_workflow(
                    anon_workflow.name,
                    [],
                    _build_named_args(ctx),
                    artifacts_dir=state.current_artifacts_dir,
                    silent=True,
                    workflow_obj=anon_workflow,
                    project=_resolve_workflow_project(ctx),
                )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/axe/run_agent_exec.py:240: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/xprompt/workflow_runner.py:553: in execute_workflow
    success = executor.execute()
              ^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <sase.xprompt.workflow_executor.WorkflowExecutor object at 0x7fb7de723530>

    def execute(self) -> bool:
        """Execute all workflow steps sequentially.
    
        Steps marked with ``finally_=True`` run even when a prior step has
        failed.  Non-finally steps are skipped after a failure.  If no
        ``finally`` steps exist the behavior is identical to before.
    
        Returns:
            True if workflow completed successfully, False otherwise.
        """
        self._save_state()
    
        # Inject workflow environment variables before any steps run
        if self.workflow.environment:
            self._inject_environment()
    
        total_steps = len(self.workflow.steps)
        has_finally_steps = any(s.finally_ for s in self.workflow.steps)
    
        # Notify workflow start
        if self.output_handler:
            self.output_handler.on_workflow_start(
                self.workflow.name,
                dict(self.context),
                total_steps,
            )
    
        # Track failure info so finally steps can still run
        failure_exception: WorkflowExecutionError | None = None
        failure_returned_false: bool = False
    
        for i, step in enumerate(self.workflow.steps):
            self.state.current_step_index = i
            step_state = self.state.steps[i]
            step_start_time = time.time()
    
            # Determine step type for display
            step_type = self._get_step_type(step)
    
            # After a failure, skip non-finally steps
            hit_failure = failure_exception is not None or failure_returned_false
            if hit_failure and not step.finally_:
                step_state.status = StepStatus.SKIPPED
                self.context[step.name] = {}
                self._save_state()
                if self.output_handler:
                    self.output_handler.on_step_start(
                        step.name, step_type, i, total_steps
                    )
                    self.output_handler.on_step_skip(
                        step.name, reason="prior step failed"
                    )
                continue
    
            # Check if step should be skipped due to provided step input
            if step.name in self._step_inputs:
                step_state.status = StepStatus.SKIPPED
                step_state.output = self._step_inputs[step.name]
                self.context[step.name] = self._step_inputs[step.name]
                self._save_state()
                if self.output_handler:
                    self.output_handler.on_step_start(
                        step.name,
                        step_type,
                        i,
                        total_steps,
                    )
                    self.output_handler.on_step_skip(
                        step.name, reason="step input provided"
                    )
                continue
    
            # Evaluate if: condition
            condition_result: bool | None = None
            if step.condition:
                condition_result = self._evaluate_condition(step.condition)
                if not condition_result:
                    step_state.status = StepStatus.SKIPPED
                    self.context[step.name] = {}
                    self._save_state()
                    # Notify step skipped
                    if self.output_handler:
                        self.output_handler.on_step_start(
                            step.name,
                            step_type,
                            i,
                            total_steps,
                            condition=step.condition,
                            condition_result=condition_result,
                        )
                        self.output_handler.on_step_skip(
                            step.name, reason="condition false"
                        )
                    continue
    
            step_state.status = StepStatus.IN_PROGRESS
            self._save_state()
    
            # Save initial "running" marker with step index for TUI display
            self._save_prompt_step_marker(
                step.name,
                step_state,
                step_type,
                step_index=i,
                hidden=step.hidden,
                output_types=self._get_output_types(i),
            )
    
            # Notify step start
            if self.output_handler:
                loop_info = self._get_loop_info(step)
                self.output_handler.on_step_start(
                    step.name,
                    step_type,
                    i,
                    total_steps,
                    condition=step.condition,
                    condition_result=condition_result,
                    loop_info=loop_info,
                )
    
            self._last_for_zero_iterations = False
    
            try:
                # Handle control flow constructs
                if step.for_loop and step.parallel_config:
                    success = self._execute_for_parallel_step(step, step_state)
                elif step.for_loop:
                    success = self._execute_for_step(step, step_state)
                elif step.repeat_config:
                    success = self._execute_repeat_step(step, step_state)
                elif step.while_config:
                    success = self._execute_while_step(step, step_state)
                elif step.parallel_config:
                    success = self._execute_parallel_step(step, step_state)
                elif step.is_agent_step():
                    success = self._execute_prompt_step(step, step_state)
                elif step.is_python_step():
                    success = self._execute_python_step(step, step_state)
                else:
                    success = self._execute_bash_step(step, step_state)
    
                if not success:
                    step_state.status = StepStatus.FAILED
                    self.state.status = "failed"
                    self._save_state()
                    if self.output_handler:
                        self.output_handler.on_workflow_failed(
                            f"Step '{step.name}' failed"
                        )
                    if not has_finally_steps:
                        return False
                    failure_returned_false = True
                    continue
    
                step_state.status = StepStatus.COMPLETED
                self._save_state()
                step_type = self._get_step_type(step)
                step_source = (
                    step.bash
                    if step_type == "bash"
                    else (step.python if step_type == "python" else None)
                )
                effective_hidden = step.hidden or (
                    step.for_loop is not None and self._last_for_zero_iterations
                )
                self._save_prompt_step_marker(
                    step.name,
                    step_state,
                    step_type,
                    step_source,
                    i,
                    hidden=effective_hidden,
                    output_types=self._get_output_types(i),
                )
    
                # Notify step complete
                if self.output_handler:
                    duration = time.time() - step_start_time
                    self.output_handler.on_step_complete(
                        step.name,
                        step_state.output,
                        duration=duration,
                    )
    
            except Exception as e:
                import traceback
    
                step_state.status = StepStatus.FAILED
                step_state.error = f"{type(e).__qualname__}: {e}"
                step_state.traceback = traceback.format_exc()
                self.state.status = "failed"
                self._save_state()
                if self.output_handler:
                    self.output_handler.on_workflow_failed(str(e))
                if not has_finally_steps:
>                   raise WorkflowExecutionError(
                        f"Step '{step.name}' failed: {e}"
                    ) from e
E                   sase.xprompt.workflow_models.WorkflowExecutionError: Step 'main' failed: Error running LLM provider command (exit code 1)
E                   stderr: FAKEY-RETRYABLE: temporarily unavailable

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/xprompt/workflow_executor.py:390: WorkflowExecutionError

During handling of the above exception, another exception occurred:

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ac...ts_retry_e2e.py', test_line=240, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14'))
tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-53/popen-gw0/test_real_fakey_completed_retr0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb8085c3620>

    async def test_real_fakey_completed_retry_chain_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        tmp_path: Path,
        monkeypatch: pytest.MonkeyPatch,
    ) -> None:
        harness = FakeyRetryHarness(
            tmp_path,
            monkeypatch,
            wait_times=[0],
            spawn_new_agent=True,
            expose_to_agent_loader=True,
            artifacts_timestamp="20260706114500",
        )
        harness.seed_running_agent(started_at=datetime(2026, 7, 6, 11, 45, 0))
        harness.use_scenario(
            monkeypatch,
            [retryable_failure("temporarily unavailable"), successful_attempt()],
        )
>       child_artifacts = harness.run_spawn_retry_chain(
            child_artifacts_timestamp="20260706115500"
        )

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py:258: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/fakey/harness.py:393: in run_spawn_retry_chain
    parent_result = self.run(prompt)
                    ^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/fakey/harness.py:432: in run
    return run_execution_loop(self.context(), f"%model:fakey-large\n{prompt}")
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/axe/run_agent_exec.py:251: in run_execution_loop
    action = handle_workflow_error(wf_exc, tracker, ctx, state)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/axe/run_agent_exec_retry.py:283: in handle_workflow_error
    spawn_result = spawn_retry_agent(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

ctx = AgentExecContext(cl_name='fakey-e2e', project_file='/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-53/popen-gw0/test_re...en=False, agent_meta={}, local_xprompts={}, multi_agent_prompt_file=None, wait_chats=[], output_variable_namespaces={})
state = LoopState(current_prompt='Your previous attempt hit a model context limit or transient provider failure. Any file edit... qa_rounds=[], feedback_bullets=[], feedback_round=0, agent_step=1, saved_chat_paths=[], original_agent_timestamp=None)
tracker = RetryTracker(retry_cfg=ProviderRetryConfig(max_retries=1, error_patterns=['FAKEY-RETRYABLE'], wait_times=[0], fallback...E: tempor..."], retry_count=1, using_fallback=False, attempt_start_epoch=1787045959.436808, execution_provider='fakey')
error_snippet = "Step 'main' failed: Error running LLM provider command (exit code 1)\nstderr: FAKEY-RETRYABLE: tempor..."
continuation_prompt = 'Your previous attempt hit a model context limit or transient provider failure. Any file edits, new tests, and other o...place, then continue implementing the plan from wherever you left off. Do not re-apply edits that are already present.'

    def spawn_retry_agent(
        *,
        ctx: AgentExecContext,
        state: LoopState,
        tracker: RetryTracker,
        error_snippet: str,
        continuation_prompt: str | None,
    ) -> dict[str, Any] | None:
        """Spawn a fresh detached child agent to retry the failing parent.
    
        Returns a dict with the child's metadata (timestamp, pid, retry_attempt,
        chain_root_timestamp, handoff_path) on success.  Returns ``None`` if
        spawn-side failure occurred and the caller should fall back to in-process
        retry.
        """
        from sase.agent.detached_child import spawn_detached_child
        from sase.telemetry.metrics import RETRY_SPAWNS_TOTAL
    
        handoff = _build_handoff(
            ctx=ctx,
            state=state,
            tracker=tracker,
            error_snippet=error_snippet,
            continuation_prompt=continuation_prompt,
        )
    
        # Write handoff into the parent's artifacts dir so diagnostic tooling
        # and the loader can read it from the parent side.
        handoff_path = handoff.write_to(ctx.artifacts_dir)
    
        child_prompt = _build_resume_prompt(handoff)
    
        extra_env: dict[str, str] = {
            ENV_RETRY_HANDOFF: handoff_path,
            ENV_RETRY_OF_TIMESTAMP: handoff.parent_timestamp,
            ENV_RETRY_ATTEMPT: str(handoff.retry_attempt),
            ENV_RETRY_CHAIN_ROOT_TIMESTAMP: handoff.chain_root_timestamp,
        }
        # Carry the fallback model selection forward to the child process.
        if handoff.use_fallback and handoff.fallback_model:
            extra_env["SASE_MODEL_OVERRIDE"] = handoff.fallback_model
    
        vcs_ref_tuple: tuple[str, str] | None = (
            (handoff.vcs_ref[0], handoff.vcs_ref[1]) if handoff.vcs_ref else None
        )
    
        try:
            result = spawn_detached_child(
                cl_name=ctx.cl_name,
                project_file=ctx.project_file,
                project_name=ctx.project_name,
                workspace_dir=ctx.workspace_dir,
                workspace_num=ctx.workspace_num,
                prompt=child_prompt,
                update_target=ctx.update_target,
                history_sort_key="",
                is_home_mode=ctx.is_home_mode,
                vcs_ref=vcs_ref_tuple,
                extra_env=extra_env,
                transfer_from_pid=os.getpid(),
            )
        except RuntimeError as exc:
            # Couldn't claim/transfer workspace.  Caller falls back to in-process.
            print(f"[retry-spawn] Failed to spawn retry agent: {exc}")
            try:
                RETRY_SPAWNS_TOTAL.labels(outcome="failed").inc()
            except Exception:
                pass
            return None
        except Exception as exc:
            print(f"[retry-spawn] Unexpected error spawning retry agent: {exc}")
            try:
                RETRY_SPAWNS_TOTAL.labels(outcome="failed").inc()
            except Exception:
                pass
            return None
    
        try:
            RETRY_SPAWNS_TOTAL.labels(outcome="ok").inc()
        except Exception:
            pass
    
        from sase.artifacts import convert_timestamp_to_artifacts_format
    
>       child_timestamp = result.timestamp
                          ^^^^^^^^^^^^^^^^
E       AttributeError: 'types.SimpleNamespace' object has no attribute 'timestamp'

/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/axe/run_agent_retry_spawn.py:324: AttributeError
----------------------------- Captured stdout call -----------------------------
╭────── 🤖 Workflow-Tmp_260818_053919-Main [Fakey-Large] Agent - Prompt ───────╮
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯

✅ Waiting for Fakey completed in 00:00╭─────── 🤖 Workflow-Tmp_260818_053919-Main [Big]_Error Agent - Prompt ────────╮
│                                                                              │
│  Exercise the retry pipeline.                                                │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
╭────── 🤖 Workflow-Tmp_260818_053919-Main [Big]_Error Agent - Response ───────╮
│                                                                              │
│  Error running LLM provider command (exit code 1)                            │
│  stderr: FAKEY-RETRYABLE: temporarily unavailable                            │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
----------------------------- Captured stderr call -----------------------------
FAKEY-RETRYABLE: temporarily unavailable
___________________ test_agents_task_bead_notes_png_snapshot ___________________
[gw0] linux -- Python 3.14.3 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.venv/bin/python

ace_png_visual = AcePngSnapshotFixture(snapshot_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ac...sase_context.py', test_line=287, repo_root=PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14'))
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fb80b720520>
tmp_path = PosixPath('/var/tmp/sase-d00a07ab/pytest-of-bryan/pytest-53/popen-gw0/test_agents_task_bead_notes_pn0')

    async def test_agents_task_bead_notes_png_snapshot(
        ace_png_visual: AcePngSnapshotFixture,
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        notes = (
            "[2026-08-01T14:03:00Z · alice] Confirmed the notes row belongs "
            "directly under the task description.\n\n"
            "[2026-08-01T14:07:00Z · bob] This second note is intentionally long "
            "enough to wrap in the BEAD lane while keeping attribution readable."
        )
        bead = BeadSummary(
            id="sase-notes.4",
            phase_title="Display persisted bead notes",
            description="Render task metadata without requiring a plan file.",
            actual_plan_path=None,
            display_plan_path=None,
            plan_exists=False,
            plan_readable=False,
            epic_title=None,
            size="medium",
            created_at="2026-07-03T13:00:00Z",
            bead_type="task",
            notes=notes,
        )
        agent = Agent(
            agent_type=AgentType.RUNNING,
            cl_name="visual-task-notes",
            project_file="/workspace/sase/visual_project.sase",
            status="RUNNING",
            start_time=datetime(2026, 8, 1, 14, 0, 0),
            raw_suffix="20260801140000",
            agent_name="sase-notes.4",
            step_type="bash",
            workspace_dir=str(tmp_path),
            llm_provider="codex",
            model="gpt-5",
        )
        monkeypatch.setattr(
            "sase.ace.tui.widgets.prompt_panel._agent_display_header_summary."
            "resolve_agent_plan_enrichment",
            lambda *_args, **_kwargs: _AgentPlanEnrichment("task", bead, None, ()),
        )
        patch_startup_loaders(monkeypatch, agents=[agent])
    
        async with AcePage(query='"visual-task-notes"', patches=patches()) as page:
            await wait_for_startup(page)
            await page.press("shift+tab")
            await page.expect_state("tab", "agents")
            await page.expect_state("agent_count", 1)
            await wait_for_svg_contains(page, "Notes:")
            await page.press("z", "z")
            await wait_for_svg_contains(page, "alice")
            await wait_for_svg_contains(page, "attribution readable")
            await wait_for_visual_idle(page)
    
            svg_plain = page.export_svg(title="ACE task BEAD notes assertion").replace(
                "&#160;",
                " ",
            )
            assert "Task Title:" in svg_plain
            assert "Description:" in svg_plain
            assert "Notes:" in svg_plain
            assert "Size:" in svg_plain
            assert "Created:" in svg_plain
            assert "2026-07-03" in svg_plain
            assert "alice" in svg_plain
            assert "bob" in svg_plain
            assert "attribution readable" in svg_plain
            assert "Epic Plan:" not in svg_plain
            assert "Epic Title:" not in svg_plain
    
>           ace_png_visual.assert_page_png(
                page,
                "agents_task_bead_notes_120x40",
                title="ACE agents task BEAD notes lane",
            )

tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py:359: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
tests/ace/tui/visual/png_diff.py:106: in assert_page_png
    self.assert_png(
tests/ace/tui/visual/png_diff.py:128: in assert_png
    assert_png_matches(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

name = 'agents_task_bead_notes_120x40'
png_bytes = b'\x89PNG\r\n\x1a\n\x00\x00\x00\rIHDR\x00\x00\x05\xca\x00\x00\x04\x02\x08\x06\x00\x00\x00\x9c\xc6\xcb \x00\x02-\xacIDA...0\x00\x00\x00\x00\x00\x8c>\xbd\xd1Ow\xf4\xf3\x9an\xdc\x994\xc0\xff\x03\x0e\x05lA5!\xc2\n\x00\x00\x00\x00IEND\xaeB`\x82'
snapshot_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/visual/snapshots/png')
artifact_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.pytest_cache/sase-visual')
update = False
node_id = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_task_bead_notes_png_snapshot'
source_svg = '<svg class="rich-terminal" viewBox="0 0 1482 1026.0" xmlns="http://www.w3.org/2000/svg">\n    <!-- Generated with Ric...y="971.6" textLength="85.4" clip-path="url(#terminal-2745154624-line-39)">dismiss</text>\n    </g>\n    </g>\n</svg>\n'
max_diff_pixels = None, max_diff_ratio = None, material_diff_threshold = None
max_material_diff_pixels = None
test_file = 'tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py'
test_line = 287
repo_root = PosixPath('/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14')

    def assert_png_matches(
        name: str,
        png_bytes: bytes,
        *,
        snapshot_root: Path,
        artifact_root: Path,
        update: bool,
        node_id: str,
        source_svg: str | None = None,
        max_diff_pixels: int | None = None,
        max_diff_ratio: float | None = None,
        material_diff_threshold: int | None = None,
        max_material_diff_pixels: int | None = None,
        test_file: str | None = None,
        test_line: int | None = None,
        repo_root: Path | None = None,
    ) -> None:
        """Assert PNG bytes against a committed golden and write diff artifacts."""
        expected_path = snapshot_path(snapshot_root, name)
        expected_repo_path = repo_relative(expected_path, repo_root)
    
        if update:
            write_bytes(expected_path, png_bytes)
            return
    
        if not expected_path.exists():
            artifacts = write_failure_artifacts(
                name=name,
                artifact_root=artifact_root,
                node_id=node_id,
                actual=png_bytes,
                expected=None,
                source_svg=source_svg,
                kind="missing_golden",
                expected_repo_path=expected_repo_path,
                test_file=test_file,
                test_line=test_line,
                repo_root=repo_root,
            )
            raise AssertionError(
                "Missing ACE PNG snapshot golden: "
                f"{expected_path}\n"
                f"Actual PNG written to: {artifacts.actual_path}\n"
                f"Summary written to: {artifacts.summary_path}\n"
                "Re-run with --sase-update-visual-snapshots to accept this "
                "snapshot intentionally."
            )
    
        tolerance = resolve_png_diff_tolerance(
            max_diff_pixels=max_diff_pixels,
            max_diff_ratio=max_diff_ratio,
            material_diff_threshold=material_diff_threshold,
            max_material_diff_pixels=max_material_diff_pixels,
        )
        expected = expected_path.read_bytes()
        # The pinned local renderer emits deterministic PNG bytes. Avoid decoding,
        # compositing, diffing, and re-encoding the overwhelmingly common exact
        # passing case. Byte differences still take the normal pixel-comparison
        # path, so equivalent encodings and every failure artifact behave exactly
        # as before.
        if expected == png_bytes:
            return
        summary, diff_png = diff_pngs(
            expected,
            png_bytes,
            material_diff_threshold=tolerance.material_diff_threshold,
        )
        if tolerance.is_within(summary):
            return
    
        artifacts = write_failure_artifacts(
            name=name,
            artifact_root=artifact_root,
            node_id=node_id,
            actual=png_bytes,
            expected=expected,
            diff=diff_png,
            source_svg=source_svg,
            summary=summary,
            tolerance=tolerance,
            kind="mismatch",
            expected_repo_path=expected_repo_path,
            test_file=test_file,
            test_line=test_line,
            repo_root=repo_root,
        )
>       raise AssertionError(
            "ACE PNG snapshot mismatch: "
            f"{expected_path}\n"
            f"Changed pixels: {summary.changed_pixels}/{summary.total_pixels} "
            f"({summary.changed_ratio:.6%}); materially changed pixels: "
            f"{summary.material_diff_pixels}/{summary.total_pixels} "
            f"({summary.material_diff_ratio:.6%}, alpha-aware color distance "
            f"> {summary.material_diff_threshold}); "
            f"allowed: {tolerance.describe()}\n"
            f"Expected PNG written to: {artifacts.expected_path}\n"
            f"Actual PNG written to: {artifacts.actual_path}\n"
            f"Diff PNG written to: {artifacts.diff_path}\n"
            f"Summary written to: {artifacts.summary_path}\n"
            "Inspect the artifacts, then re-run with "
            "--sase-update-visual-snapshots only for intentional changes."
        )
E       AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/visual/snapshots/png/agents_task_bead_notes_120x40.png
E       Changed pixels: 10724/1520532 (0.705279%); materially changed pixels: 10676/1520532 (0.702123%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
E       Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_task_bead_notes_png_snapshot/agents_task_bead_notes_120x40/expected.png
E       Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_task_bead_notes_png_snapshot/agents_task_bead_notes_120x40/actual.png
E       Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_task_bead_notes_png_snapshot/agents_task_bead_notes_120x40/diff.png
E       Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_task_bead_notes_png_snapshot/agents_task_bead_notes_120x40/summary.txt
E       Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.

tests/ace/tui/visual/png_diff.py:281: AssertionError
============================= slowest 20 durations =============================
31.74s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
18.76s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
13.43s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
11.03s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_bullet_highlight_solo_png_snapshot[textual-dark-prompt_bullet_highlight_solo_dark_120x40-ACE prompt input \u2014 bullet-dash highlighting, dark theme]
10.84s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_phase_family_bead_and_plan_context_png_snapshot
10.83s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_clean_png_snapshot
10.63s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_readonly_png_snapshot
10.59s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_new_png_snapshot
10.29s call     tests/ace/tui/visual/test_ace_png_snapshots_vcs_repo_completion.py::test_vcs_repo_completion_panel_png_snapshot
9.81s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_target_completion.py::test_fork_target_completion_png_snapshot
9.69s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
9.64s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_parked_png_snapshot
9.61s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_submit_choice_modal_png_snapshot
9.25s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_dirty_png_snapshot
9.11s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_codeblock_highlight_solo_png_snapshot[textual-light-prompt_codeblock_highlight_solo_light_120x40-ACE prompt input \u2014 code highlighting, light theme]
9.01s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_bullet_highlight_solo_png_snapshot[textual-light-prompt_bullet_highlight_solo_light_120x40-ACE prompt input \u2014 bullet-dash highlighting, light theme]
9.01s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_misspelling_highlight_png_snapshot[textual-dark-prompt_misspelling_highlight_dark_120x40-ACE prompt input \u2014 sticky misspelling highlighting, dark theme]
8.96s call     tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_raw_diagnostics_png_snapshot
8.93s call     tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py::test_model_completion_mixed_menu_png_snapshot
8.84s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_xprompt_highlight_solo_light_png_snapshot
=========================== short test summary info ============================
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_completed_retry_chain_png_snapshot - AttributeError: 'types.SimpleNamespace' object has no attribute 'timestamp'
FAILED tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_task_bead_notes_png_snapshot - AssertionError: ACE PNG snapshot mismatch: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/tests/ace/tui/visual/snapshots/png/agents_task_bead_notes_120x40.png
Changed pixels: 10724/1520532 (0.705279%); materially changed pixels: 10676/1520532 (0.702123%, alpha-aware color distance > 8); allowed: 0 pixels, 0.000000%, and 0 material pixels above alpha-aware color distance 8 (default)
Expected PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_task_bead_notes_png_snapshot/agents_task_bead_notes_120x40/expected.png
Actual PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_task_bead_notes_png_snapshot/agents_task_bead_notes_120x40/actual.png
Diff PNG written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_task_bead_notes_png_snapshot/agents_task_bead_notes_120x40/diff.png
Summary written to: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/.pytest_cache/sase-visual/tests_ace_tui_visual_test_ace_png_snapshots_agents_sase_context.py__test_agents_task_bead_notes_png_snapshot/agents_task_bead_notes_120x40/summary.txt
Inspect the artifacts, then re-run with --sase-update-visual-snapshots only for intentional changes.
============= 2 failed, 710 passed, 1 skipped in 464.93s (0:07:44) =============
error: recipe `test-visual` failed on line 471 with exit code 1

