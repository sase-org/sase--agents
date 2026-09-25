# Chat History - ace-run (sase-126.4--mon-a)

- **TIMESTAMP:** 2026-09-18 02:53:00 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-126.4--mon-a

## Prompt

sase monitor start --command 'just install && just fix && just check && just test-visual && just phase7-perf-check && just check-full' --reason 'Run integrated verification for bead sase-126.4 after registering the usage-probes managed-temp reaper horizon'

## Response

[install] Installing local sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core for local dev.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-wheels/db4ece99d0947094d80d77f1048f98580a1317c29229d7be540fdd21777fb7c3/sase_core_rs-0.34.50-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 3ms
Prepared 1 package in 5ms
Uninstalled 1 package in 3ms
Installed 1 package in 13ms
 ~ sase-core-rs==0.34.50 (from file:///home/bryan/.sase/cache/sase-core-wheels/db4ece99d0947094d80d77f1048f98580a1317c29229d7be540fdd21777fb7c3/sase_core_rs-0.34.50-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
    Finished `dev-update` profile [optimized] target(s) in 0.76s
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/sase-xprompt-lsp
uv pip install --python .venv/bin/python --no-sources $(just _core-overrides-arg) -e ".[dev]"
Resolved 97 packages in 367ms
   Building sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
      Built sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
Prepared 1 package in 629ms
Uninstalled 1 package in 9ms
Installed 1 package in 6ms
 ~ sase==0.17.1 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix                      │
└───────────────────────────────────────────────────────┘

---------- Formatting Python with ruff... ----------
.venv-format/bin/ruff format src/ tests/
9373 files left unchanged

---------- Fixing Python with ruff... ----------
.venv-format/bin/ruff check --fix src/ tests/
All checks passed!

---------- Rendering generated docs... ----------
.venv-format/bin/python tools/render_model_alias_docs

---------- Formatting Markdown with prettier... ----------
node_modules/.bin/prettier --write "**/*.md"
AGENTS.md 106ms (unchanged)
CLAUDE.md 62ms (unchanged)
CONTRIBUTING.md 7ms (unchanged)
demos/README.md 46ms (unchanged)
demos/tapes/AGENTS.md 3ms (unchanged)
demos/tapes/CLAUDE.md 3ms (unchanged)
demos/tapes/GEMINI.md 3ms (unchanged)
demos/tapes/OPENCODE.md 3ms (unchanged)
demos/tapes/QWEN.md 2ms (unchanged)
docs/ace.md 1831ms (unchanged)
docs/acknowledgements.md 23ms (unchanged)
docs/agent_families.md 95ms (unchanged)
docs/agent_images.md 96ms (unchanged)
docs/agent_providers.md 44ms (unchanged)
docs/agents_sidecar.md 55ms (unchanged)
docs/architecture.md 39ms (unchanged)
docs/artifact_links.md 34ms (unchanged)
docs/artifact_references.md 38ms (unchanged)
docs/artifacts_pane_contract.md 26ms (unchanged)
docs/artifacts_pane_visual_grammar.md 41ms (unchanged)
docs/axe.md 237ms (unchanged)
docs/beads.md 311ms (unchanged)
docs/blog/index.md 3ms (unchanged)
docs/blog/posts/axe-background-daemon.md 32ms (unchanged)
docs/blog/posts/beads-and-sdd.md 24ms (unchanged)
docs/blog/posts/changespecs-in-practice.md 22ms (unchanged)
docs/blog/posts/commit-workflows-plugins.md 22ms (unchanged)
docs/blog/posts/hello-sase-your-first-15-minutes.md 28ms (unchanged)
docs/blog/posts/prompt-widget-and-nvim.md 33ms (unchanged)
docs/blog/posts/structured-agentic-software-engineering.md 52ms (unchanged)
docs/blog/posts/telegram-mobile-agents.md 29ms (unchanged)
docs/blog/posts/whats-next-memory-mobile-web.md 16ms (unchanged)
docs/blog/posts/why-coding-agents-need-orchestration.md 81ms (unchanged)
docs/blog/posts/xprompts-in-depth.md 26ms (unchanged)
docs/change_spec.md 34ms (unchanged)
docs/cli.md 169ms (unchanged)
docs/commit_workflows.md 117ms (unchanged)
docs/completion.md 50ms (unchanged)
docs/configuration.md 1629ms (unchanged)
docs/content_layout.md 21ms (unchanged)
docs/development.md 213ms (unchanged)
docs/editor.md 69ms (unchanged)
docs/fakey.md 15ms (unchanged)
docs/getting_started.md 41ms (unchanged)
docs/images/blog/one_prompt_provider_clis.prompt.md 6ms (unchanged)
docs/images/blog/prompt_burrito.prompt.md 6ms (unchanged)
docs/images/blog/window_farm_vs_control_tower.prompt.md 6ms (unchanged)
docs/images/commit-workflow-infographic.critique.md 22ms (unchanged)
docs/images/commit-workflow-infographic.prompt.md 12ms (unchanged)
docs/images/infographic-style-brief.md 16ms (unchanged)
docs/images/rust-backend-boundary-infographic.critique.md 34ms (unchanged)
docs/images/rust-backend-boundary-infographic.prompt.md 5ms (unchanged)
docs/images/sase_overview.critique.md 6ms (unchanged)
docs/images/sase_overview.prompt.md 6ms (unchanged)
docs/images/sase_tui_tabs_infographic.critique.md 31ms (unchanged)
docs/images/sase_tui_tabs_infographic.prompt.md 5ms (unchanged)
docs/images/sase-rust-core-integration.critique.md 28ms (unchanged)
docs/images/sase-rust-core-integration.prompt.md 3ms (unchanged)
docs/images/sase-telegram-integration.critique.md 25ms (unchanged)
docs/images/sase-telegram-integration.prompt.md 10ms (unchanged)
docs/images/workflow-execution-infographic.critique.md 42ms (unchanged)
docs/images/workflow-execution-infographic.prompt.md 10ms (unchanged)
docs/images/xprompt-resolution-infographic.critique.md 7ms (unchanged)
docs/images/xprompt-resolution-infographic.prompt.md 8ms (unchanged)
docs/images/zorg-zettel-vision-infographic.critique.md 49ms (unchanged)
docs/index.md 7ms (unchanged)
docs/init.md 93ms (unchanged)
docs/integrations.md 35ms (unchanged)
docs/llms.md 407ms (unchanged)
docs/memory.md 43ms (unchanged)
docs/mentors.md 28ms (unchanged)
docs/mobile_gateway.md 49ms (unchanged)
docs/mobile_mvp_runbook.md 34ms (unchanged)
docs/monitors.md 89ms (unchanged)
docs/notifications.md 215ms (unchanged)
docs/pager.md 31ms (unchanged)
docs/perf_runbook.md 121ms (unchanged)
docs/plugins.md 103ms (unchanged)
docs/project_spec.md 37ms (unchanged)
docs/prompt.md 30ms (unchanged)
docs/query_language.md 21ms (unchanged)
docs/remote_dispatch.md 30ms (unchanged)
docs/rust_backend.md 100ms (unchanged)
docs/sdd_storage.md 44ms (unchanged)
docs/sdd.md 92ms (unchanged)
docs/sudo.md 35ms (unchanged)
docs/telemetry.md 39ms (unchanged)
docs/troubleshooting/agent-revival.md 7ms (unchanged)
docs/troubleshooting/runner-slots.md 25ms (unchanged)
docs/vcs.md 85ms (unchanged)
docs/workflow_spec.md 102ms (unchanged)
docs/workspace.md 79ms (unchanged)
docs/xprompt.md 418ms (unchanged)
GEMINI.md 28ms (unchanged)
INSTALL.md 22ms (unchanged)
OPENCODE.md 28ms (unchanged)
QWEN.md 29ms (unchanged)
README.md 14ms (unchanged)
sase/memory/cli_rules.md 5ms (unchanged)
sase/memory/decisions.md 10ms (unchanged)
sase/memory/decisions/agents-sync-publish-only.md 8ms (unchanged)
sase/memory/decisions/ci-two-speed-split.md 6ms (unchanged)
sase/memory/decisions/corpus-before-mechanism.md 5ms (unchanged)
sase/memory/decisions/gates-never-block.md 7ms (unchanged)
sase/memory/decisions/host-owned-completion.md 6ms (unchanged)
sase/memory/decisions/memory-links-are-authored.md 6ms (unchanged)
sase/memory/decisions/memory-webs.md 6ms (unchanged)
sase/memory/decisions/record-before-admit.md 7ms (unchanged)
sase/memory/decisions/rust-core-required.md 5ms (unchanged)
sase/memory/decisions/single-turn-agents.md 5ms (unchanged)
sase/memory/decisions/two-speed-verification.md 5ms (unchanged)
sase/memory/decisions/v1-import-retired.md 7ms (unchanged)
sase/memory/decisions/webs-render-in-their-own-section.md 6ms (unchanged)
sase/memory/generated_skills.md 8ms (unchanged)
sase/memory/glossary.md 3ms (unchanged)
sase/memory/glossary/agent-clan.md 1ms (unchanged)
sase/memory/glossary/agent-family.md 2ms (unchanged)
sase/memory/glossary/agent-hood.md 2ms (unchanged)
sase/memory/glossary/agent-instruction-file.md 2ms (unchanged)
sase/memory/glossary/agent-neighbor.md 2ms (unchanged)
sase/memory/glossary/agent-node.md 2ms (unchanged)
sase/memory/glossary/agent-shell.md 1ms (unchanged)
sase/memory/glossary/agent-tribe.md 2ms (unchanged)
sase/memory/glossary/artifact-markdown-file.md 2ms (unchanged)
sase/memory/glossary/artifact-reference.md 2ms (unchanged)
sase/memory/glossary/artifact.md 2ms (unchanged)
sase/memory/glossary/chop.md 2ms (unchanged)
sase/memory/glossary/core-memory.md 1ms (unchanged)
sase/memory/glossary/current-project.md 2ms (unchanged)
sase/memory/glossary/feature-flag.md 1ms (unchanged)
sase/memory/glossary/flag-bead.md 2ms (unchanged)
sase/memory/glossary/gate-shell.md 3ms (unchanged)
sase/memory/glossary/lumberjack.md 2ms (unchanged)
sase/memory/glossary/memory-strand.md 1ms (unchanged)
sase/memory/glossary/memory-web.md 2ms (unchanged)
sase/memory/glossary/patch.md 2ms (unchanged)
sase/memory/glossary/proc-shell.md 2ms (unchanged)
sase/memory/glossary/proc.md 2ms (unchanged)
sase/memory/glossary/reference-memory.md 2ms (unchanged)
sase/memory/glossary/required-plugin.md 2ms (unchanged)
sase/memory/glossary/sase-agent.md 2ms (unchanged)
sase/memory/glossary/sase-gate.md 4ms (unchanged)
sase/memory/glossary/sase-monitor.md 2ms (unchanged)
sase/memory/glossary/sase-node.md 2ms (unchanged)
sase/memory/glossary/sase-project.md 2ms (unchanged)
sase/memory/glossary/sase-repo.md 1ms (unchanged)
sase/memory/glossary/sase-shell.md 2ms (unchanged)
sase/memory/glossary/sase-workspace.md 2ms (unchanged)
sase/memory/glossary/stitch.md 2ms (unchanged)
sase/memory/glossary/strand-keyword.md 2ms (unchanged)
sase/memory/glossary/task-type.md 3ms (unchanged)
sase/memory/glossary/usage-window.md 3ms (unchanged)
sase/memory/glossary/xprompt-memory.md 2ms (unchanged)
sase/memory/glossary/xprompt-part.md 1ms (unchanged)
sase/memory/glossary/xprompt-swarm.md 2ms (unchanged)
sase/memory/glossary/xprompt-workflow.md 1ms (unchanged)
sase/memory/glossary/xprompt.md 1ms (unchanged)
sase/memory/gotchas.md 1ms (unchanged)
sase/memory/lint_and_test.md 6ms (unchanged)
sase/memory/README.md 26ms (unchanged)
sase/memory/rust_core_backend_boundary.md 3ms (unchanged)
sase/memory/sase_artifacts.md 14ms (unchanged)
sase/memory/sase_beads.md 18ms (unchanged)
sase/memory/sase_flags.md 12ms (unchanged)
sase/memory/sase_sizes.md 6ms (unchanged)
sase/memory/sase.md 9ms (unchanged)
sase/memory/symvision.md 14ms (unchanged)
sase/memory/task_types.md 5ms (unchanged)
sase/memory/task_types/bug.md 7ms (unchanged)
sase/memory/task_types/ci.md 7ms (unchanged)
sase/memory/task_types/feature.md 6ms (unchanged)
sase/memory/task_types/flake.md 6ms (unchanged)
sase/memory/task_types/memory.md 5ms (unchanged)
sase/memory/tui_perf.md 16ms (unchanged)
sase/memory/xprompts.md 14ms (unchanged)
smoke/pypi/README.md 5ms (unchanged)
src/sase/ace/AGENTS.md 5ms (unchanged)
src/sase/ace/CLAUDE.md 5ms (unchanged)
src/sase/ace/GEMINI.md 5ms (unchanged)
src/sase/ace/OPENCODE.md 5ms (unchanged)
src/sase/ace/QWEN.md 5ms (unchanged)
src/sase/ace/tui/fonts/README.md 6ms (unchanged)
src/sase/amd/templates/AGENTS.minimal.template.md 1ms (unchanged)
src/sase/amd/templates/AGENTS.template.md 1ms (unchanged)
src/sase/memory/assets/memory-directory-map.prompt.md 8ms (unchanged)
src/sase/sdd/assets/agents-directory-map.png.prompt.md 7ms (unchanged)
src/sase/sdd/assets/beads-directory-map.png.prompt.md 6ms (unchanged)
src/sase/sdd/assets/plans-directory-map.png.prompt.md 5ms (unchanged)
src/sase/sdd/assets/research-directory-map.png.prompt.md 5ms (unchanged)
src/sase/xprompts/coder.md 2ms (unchanged)
src/sase/xprompts/fix_hook.md 2ms (unchanged)
src/sase/xprompts/skills/sase_agents_status.md 12ms (unchanged)
src/sase/xprompts/skills/sase_chats.md 11ms (unchanged)
src/sase/xprompts/skills/sase_final.md 13ms (unchanged)
src/sase/xprompts/skills/sase_gate.md 35ms (unchanged)
src/sase/xprompts/skills/sase_git_commit.md 19ms (unchanged)
src/sase/xprompts/skills/sase_memory_read.md 7ms (unchanged)
src/sase/xprompts/skills/sase_memory_write.md 8ms (unchanged)
src/sase/xprompts/skills/sase_monitor.md 19ms (unchanged)
src/sase/xprompts/skills/sase_new_task.md 11ms (unchanged)
src/sase/xprompts/skills/sase_notify.md 9ms (unchanged)
src/sase/xprompts/skills/sase_patches.md 14ms (unchanged)
src/sase/xprompts/skills/sase_pipe.md 7ms (unchanged)
src/sase/xprompts/skills/sase_plan.md 6ms (unchanged)
src/sase/xprompts/skills/sase_project.md 4ms (unchanged)
src/sase/xprompts/skills/sase_questions.md 6ms (unchanged)
src/sase/xprompts/skills/sase_repo.md 9ms (unchanged)
src/sase/xprompts/skills/sase_run.md 21ms (unchanged)
src/sase/xprompts/skills/sase_sudo.md 7ms (unchanged)
src/sase/xprompts/skills/sase_var.md 9ms (unchanged)
src/sase/xprompts/skills/SKILL.frame.template.md 1ms (unchanged)
src/sase/xprompts/split_file.md 2ms (unchanged)
src/sase/xprompts/summarize.md 2ms (unchanged)
src/sase/xprompts/t.md 1ms (unchanged)
src/sase/xprompts/tribe.md 1ms (unchanged)
tests/ace/tui/artifacts_contract/fixtures/notes/hello__a.md 1ms (unchanged)
tests/ace/tui/artifacts_contract/fixtures/notes/hello.md 1ms (unchanged)
tests/ace/tui/repro/README.md 4ms (unchanged)
tests/fixtures/agy/README.md 2ms (unchanged)
tests/fixtures/codex_stream/README.md 2ms (unchanged)
tests/fixtures/qwen_stream/README.md 1ms (unchanged)
tests/perf/README.md 18ms (unchanged)
tests/plan_chain_golden/README.md 3ms (unchanged)
tools/AGENTS.md 8ms (unchanged)
tools/CLAUDE.md 8ms (unchanged)
tools/GEMINI.md 8ms (unchanged)
tools/OPENCODE.md 9ms (unchanged)
tools/QWEN.md 8ms (unchanged)

---------- Fixing keep-sorted blocks in YAML files... ----------
git ls-files -z '*.yml' '*.yaml' | xargs -0 -r sh -c 'for path do [ ! -e "$path" ] || printf "%s\0" "$path"; done' sh | xargs -0 -r .venv-format/bin/keep-sorted
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
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
[core-floor-probe] stale_actionable: sase-core-rs==0.34.47 is missing 4 capability(s) that exist in a published sase-core release.
[core-floor-probe] service_enablement_resolve: first appears in sase-core fe7c4a0 (feat(service): add status snapshot wire); release v0.34.48 contains it.
[core-floor-probe] service_status_build: first appears in sase-core fe7c4a0 (feat(service): add status snapshot wire); release v0.34.48 contains it.
[core-floor-probe] service_status_read: first appears in sase-core fe7c4a0 (feat(service): add status snapshot wire); release v0.34.48 contains it.
[core-floor-probe] service_status_write: first appears in sase-core fe7c4a0 (feat(service): add status snapshot wire); release v0.34.48 contains it.
{"cache_hit": true, "capabilities": [{"commit": "fe7c4a0", "name": "service_enablement_resolve", "release": "v0.34.48", "subject": "feat(service): add status snapshot wire"}, {"commit": "fe7c4a0", "name": "service_status_build", "release": "v0.34.48", "subject": "feat(service): add status snapshot wire"}, {"commit": "fe7c4a0", "name": "service_status_read", "release": "v0.34.48", "subject": "feat(service): add status snapshot wire"}, {"commit": "fe7c4a0", "name": "service_status_write", "release": "v0.34.48", "subject": "feat(service): add status snapshot wire"}], "declared_floor": "0.34.47", "exit_code": 3, "message": "sase-core-rs==0.34.47 is missing 4 capability(s) that exist in a published sase-core release.", "status": "stale_actionable"}
✓ committed plans
✓ test (scoped)
scoped: selected 502 of 3972 test files (12.6%; rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); contexts baseline stale; est 963s/444s; gear 4 workers
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-visual              │
└───────────────────────────────────────────────────────┘

---------- Running visual pytest subset... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 12/12 workers
12 workers [960 items]

........................................................................ [  7%]
........................................................................ [ 15%]
........................................................................ [ 22%]
........................................................................ [ 30%]
........................................................................ [ 37%]
........................................................................ [ 45%]
........................................................................ [ 52%]
........................................................................ [ 60%]
........................................................................ [ 67%]
........................................................................ [ 75%]
........................................................................ [ 82%]
........................................................................ [ 90%]
........................................................................ [ 97%]
........................                                                 [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: 12 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
39.78s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
19.44s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_weighted_runner_capacity_png_snapshots
14.43s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_dirty_png_snapshot
14.15s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
13.86s call     tests/ace/tui/visual/test_ace_png_snapshots_frontmatter_panel.py::test_frontmatter_panel_saved_feedback_png_snapshot
13.83s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_active_upper_png_snapshot
13.73s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_targeted_clean_png_snapshot
13.21s call     tests/ace/tui/visual/test_ace_png_snapshots_at_reference_completion.py::test_truncated_at_reference_payload_panel_png_snapshot
13.16s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_stale_png_snapshot
13.13s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_xprompt_highlight_solo_light_png_snapshot
12.99s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_new_and_clean_png_snapshots[True-mini_xprompt_pane_clean_light_120x40-ACE mini-xprompt pane - clean light]
12.77s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_retry_countdown_png_snapshot
12.60s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_dirty_png_snapshot
12.25s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
12.20s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_family_panel.py::test_family_panel_fold_levels_and_member_override_png_snapshots
12.02s call     tests/ace/tui/visual/test_ace_png_snapshots_model_explicit_completion.py::test_model_explicit_completion_full_menu_png_snapshot[light]
11.79s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_skill_completion.py::test_prompt_skill_completion_long_description_png_snapshot
11.69s call     tests/ace/tui/visual/test_ace_png_snapshots_model_completion.py::test_model_completion_alias_only_menu_png_snapshot
11.67s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_misspelling_highlight_png_snapshot[textual-dark-prompt_misspelling_highlight_dark_120x40-ACE prompt input \u2014 sticky misspelling highlighting, dark theme]
11.58s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_completion_panel_png_snapshot
=========== 960 passed, 1 skipped, 12 warnings in 298.43s (0:04:58) ============
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

---------- Phase 7E regression floor (sase-1e.5) ----------
.venv/bin/python tests/perf/phase7_check_regression.py 

==== Phase 7E floor: bench_core_parse ====

# golden_myproj (947 bytes)
  runs=15 warmup=3
  rust_available=True
  scenario               min_ms    median_ms     p95_ms     max_ms
  ----------------------------------------------------------------
  python_direct           0.126        0.131      0.146      0.177
  rust_direct             0.044        0.045      0.047      0.052
  rust_facade             0.071        0.072      0.074      0.077

# synthetic_200_specs (118008 bytes)
  runs=15 warmup=3
  rust_available=True
  scenario               min_ms    median_ms     p95_ms     max_ms
  ----------------------------------------------------------------
  python_direct          12.313       12.715     13.196     13.259
  rust_direct             4.597        4.816      5.158      5.474
  rust_facade             6.333        6.707      7.156      7.418

==== Phase 7E floor: bench_core_query ====

# parse_only
  query='"feature" OR status:Ready'
  scenario                         min_ms    median_ms     p95_ms     max_ms
  --------------------------------------------------------------------------
  python_direct_parse               0.009        0.009      0.012      0.012
  python_facade_parse               0.024        0.024      0.026      0.027
  rust_direct_parse                 0.006        0.006      0.008      0.008
  rust_facade_parse                 0.024        0.024      0.030      0.037

# synthetic_100_specs (100 specs)
  query='"feature" OR status:Ready'
  scenario                         min_ms    median_ms     p95_ms     max_ms
  --------------------------------------------------------------------------
  python_direct_parse               0.009        0.009      0.011      0.019
  python_facade_parse               0.024        0.025      0.028      0.029
  python_parse_and_evaluate         0.448        0.452      0.467      0.486
  reference_python_batch_evaluate_many      0.443        0.446      0.456      0.484
  rust_one_shot_diagnostic_evaluate_many      4.976        5.159      7.163      7.478
  rust_persistent_corpus_compile      7.106        7.273     13.181     13.220
  rust_persistent_fully_compiled_evaluate_many      0.014        0.014      0.014      0.014
  rust_persistent_query_keystroke_evaluate_many      0.016        0.017      0.017      0.017

# synthetic_1000_specs (1000 specs)
  query='"feature" OR status:Ready'
  scenario                         min_ms    median_ms     p95_ms     max_ms
  --------------------------------------------------------------------------
  python_direct_parse               0.009        0.009      0.010      0.010
  python_facade_parse               0.024        0.025      0.029      0.030
  python_parse_and_evaluate         4.126        4.532      7.063      7.735
  reference_python_batch_evaluate_many      4.250        4.275      4.563      5.037
  rust_one_shot_diagnostic_evaluate_many     53.246       54.915     62.721     66.336
  rust_persistent_corpus_compile     84.720       87.023    136.876    141.881
  rust_persistent_fully_compiled_evaluate_many      0.149        0.151      0.158      0.160
  rust_persistent_query_keystroke_evaluate_many      0.150        0.154      0.160      0.163

# home_tree [skipped]
  reason=pass --include-home-tree for local-only home-tree measurement

==== Phase 7E floor: bench_agent_scan ====

# synthetic_6p_200pp
  projects_root=/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws10-260918_015739/tmpogad89ku/projects
  runs=8 warmup=2 target_name='proj001_agent_0000' workflow_name='wf_0'
  scenario                                 min_ms    median_ms     p95_ms     max_ms
  ----------------------------------------------------------------------------------
  find_named_agent                          0.187        0.205      0.220      0.220
  is_workflow_complete                      0.138        0.145      0.152      0.152
  list_running_agents                       0.253        0.266      0.284      0.284
  list_all_agents                           0.240        0.244      0.252      0.252
  list_running_agents_shared_snapshot     214.859      226.549    296.422    296.422
  list_all_agents_shared_snapshot         220.475      226.539    279.573    279.573
  tui_artifact_load                         0.212        0.229      0.241      0.241
  scan_rust_to_dict                       147.936      154.067    158.708    158.708
  scan_rust_dict_to_wire                  234.934      241.100    325.178    325.178
  scan_rust_facade                        237.062      243.380    341.067    341.067
  scan_rust_capacity_facade                20.549       21.209     23.579     23.579

==== Phase 7E floor: bench_status_state_machine ====

# golden_myproj_pure (947 bytes)
  runs=200 warmup=20 target_name='beta'
  scenario                                             min_us    median_us     p95_us     max_us
  ----------------------------------------------------------------------------------------------
  is_valid_transition                                   3.476        3.536      6.242     40.096
  remove_workspace_suffix                               1.052        1.072      1.112      1.222
  read_status_from_lines                                2.725        3.056      3.096      3.227
  apply_status_update                                   3.206        3.536      3.567      3.617
  plan_status_transition                               17.073       17.384     17.684     35.368

# golden_myproj_transition (947 bytes)
  runs=5 warmup=10 target_name='beta'
  scenario                                             min_us    median_us     p95_us     max_us
  ----------------------------------------------------------------------------------------------
  transition_patch_status_wip_to_draft                588.745      591.520   1896.944   1896.944
  transition_patch_status_wip_to_ready                578.355      585.679    620.505    620.505

# synthetic_200_specs_pure (113918 bytes)
  runs=200 warmup=20 target_name='spec-199'
  scenario                                             min_us    median_us     p95_us     max_us
  ----------------------------------------------------------------------------------------------
  is_valid_transition                                   3.536        3.577      3.777      4.639
  remove_workspace_suffix                               1.072        1.082      1.122      1.272
  read_status_from_lines                              308.769      326.153    386.077   1133.605
  apply_status_update                                 349.427      356.927    368.945    382.661
  plan_status_transition                               17.173       17.574     17.934     29.256

# synthetic_200_specs_transition (113918 bytes)
  runs=5 warmup=10 target_name='spec-199'
  scenario                                             min_us    median_us     p95_us     max_us
  ----------------------------------------------------------------------------------------------
  transition_patch_status_wip_to_draft              14810.849    15287.770  17605.466  17605.466
  transition_patch_status_wip_to_ready              14964.274    16427.487  16592.833  16592.833

==== Phase 7 floor: bench_notification_store ====

==== Phase 7E floor check results ====
  rust_slowdown_factor = 1.40x phase7b rust median
  [PASS] parse_project_bytes.golden_myproj.facade: rust=72.07us python=n/a ceiling=174.09us must_beat_python=False
        note: scenario 'facade' missing from baseline (python) summaries
  [PASS] parse_project_bytes.synthetic_200_specs.facade: rust=6706.98us python=n/a ceiling=26762.65us must_beat_python=False
        note: scenario 'facade' missing from baseline (python) summaries
  [PASS] parse_query.parse_only.direct: rust=6.38us python=9.49us ceiling=8.08us must_beat_python=True
  [PASS] evaluate_query_many.synthetic_1000_specs.persistent_query_keystroke: rust=153.63us python=4274.50us ceiling=193.44us must_beat_python=True
        note: absolute floor uses per-anchor rust_slowdown_factor 2.90x instead of global 1.40x: The Phase 7B / query-corpus capture (66.70us) is not a portable absolute baseline for this microsecond-scale product route; the same-process must_beat_python gate remains the hardware-independent contract. Eight consecutive master CI perf-floors reports (runs 32532695452, 32537985517, 32542973465, 32546975028, 32551370513, 32555295598, 32558460537, 32568874089) measured 178.28-184.36us while still beating live Python by ~29-30x, and a clean local reproduction measured 147.07us. Use a 2.90x absolute floor (~193.44us), roughly 4.9% above the worst hosted median (184.36us in run 32558460537), to cover GitHub-hosted runner heterogeneity while preserving the global 1.4x gate for stable anchors. This still fails a material regression beyond the observed hosted envelope (2x the hosted max is ~368.72us, about 1.9x the new ceiling). Revisit once hosted medians stabilize near a recaptured baseline on current GitHub runners.
  [PASS] scan_agent_artifacts.synthetic_6p_200pp.scan_facade: rust=243380.37us python=n/a ceiling=281973.47us must_beat_python=False
        note: scenario 'scan_facade' missing from baseline (python) summaries
        note: absolute floor uses per-anchor rust_slowdown_factor 2.35x instead of global 1.40x: The Phase 7B baseline (~120 ms) predates several intentional agent-scan wire-shape expansions: pending_question.json marker scanning, workspace_dir / agent-meta tag / PDF activity / image paths / workflow-relationship / epic-start fields on agent_meta and done markers. On the 6-project x 200-per-project synthetic each addition increases both serde parsing on the Rust side and per-record Python dataclass hydration. CI, not local host timing, sets this floor: master CI perf-floors runs from 2026-08-13T22:45Z through 2026-08-14T20:56Z, including CI run IDs 31838558537 and 31840230310, produced observed medians from 146.81 ms through 269.78 ms, with run 31840230310 failing the old 2.15x ceiling at 266.26 ms. Use a 2.35x absolute floor (~282 ms), roughly 4.5% above the worst observed CI median, to cover GitHub-hosted runner heterogeneity while preserving the global 1.4x gate for stable anchors. This still catches a real facade regression that pushes the current CI distribution materially beyond the observed envelope. Revisit when Python hydration is pushed across the PyO3 boundary.
  [PASS] scan_agent_artifacts.synthetic_6p_200pp.capacity_scan_facade: rust=21208.50us python=n/a ceiling=40908.14us must_beat_python=False
        note: scenario 'capacity_scan_facade' missing from baseline (python) summaries
        note: absolute floor uses per-anchor rust_slowdown_factor 2.00x instead of global 1.40x: Phase 4 (sase-za.4) capacity-only scan anchor added alongside the slot-poll-diet fix (sase-za.1/sase-za.2) that made runner-slot admission use this mode. No CI history exists yet: three back-to-back local captures on a busy shared dev host ranged 20.15-30.91 ms against a mostly-done 1,200-dir synthetic tree (1,100 done / 100 running), already a ~1.5x spread from host contention alone. Use a 2.0x absolute floor (~41 ms) on the ~20.45 ms captured median to leave detection margin once CI history accumulates; tighten in a follow-up once master perf-floors runs establish a stable envelope, mirroring how scan_facade above was tightened from CI observations.
  [PASS] notification_store.mostly_dismissed_900.notification_store_mostly_dismissed_load_snapshot: rust=60.17us python=n/a ceiling=189.00us must_beat_python=False
        note: scenario 'notification_store_mostly_dismissed_load_snapshot' missing from baseline (python) summaries
  [PASS] apply_status_update.golden_myproj_pure.apply_status_update: rust=3.54us python=n/a ceiling=8.12us must_beat_python=False
        note: scenario 'apply_status_update' missing from baseline (python) summaries
  [PASS] notification_store.synthetic_5k.notification_store_5k_load_snapshot: rust=8673.45us python=n/a ceiling=18466.00us must_beat_python=False
        note: scenario 'notification_store_5k_load_snapshot' missing from baseline (python) summaries
  [PASS] notification_store.synthetic_5k.notification_store_5k_mark_dismissed_burst: rust=60615.09us python=n/a ceiling=6811056.00us must_beat_python=False
        note: scenario 'notification_store_5k_mark_dismissed_burst' missing from baseline (python) summaries
  [PASS] notification_store.synthetic_5k.notification_store_5k_mark_all_read: rust=57994.09us python=n/a ceiling=215055.00us must_beat_python=False
        note: scenario 'notification_store_5k_mark_all_read' missing from baseline (python) summaries
        note: absolute floor uses per-anchor rust_slowdown_factor 3.00x instead of global 1.40x: This full-store read-state mutation uses the production JSONL lock/tempfile/rename write path and showed GitHub-hosted runner IO variance at 194856us with a 157549us confirmation while sibling write-heavy notification anchors were also elevated 3-4x. Typical CI medians are near 47500us, so a 3.0x Phase 7B ceiling (~215055us) still leaves roughly a 4.5x detection margin for a real regression and remains the tightest notification-store write gate.
  [PASS] notification_store.synthetic_5k.notification_store_append_plus_rewrite_concurrency: rust=656547.75us python=n/a ceiling=2717251.60us must_beat_python=False
        note: scenario 'notification_store_append_plus_rewrite_concurrency' missing from baseline (python) summaries
  [PASS] notification_store.synthetic_5k.notification_modal_dismiss_burst: rust=881745.69us python=n/a ceiling=5098492.80us must_beat_python=False
        note: scenario 'notification_modal_dismiss_burst' missing from baseline (python) summaries
        note: absolute floor uses per-anchor rust_slowdown_factor 1.60x instead of global 1.40x: This modal path performs 25 production one-at-a-time persisted dismissals from a loaded 5k inbox and has shown multi-second GitHub-hosted runner IO variance; keep the extra slack local to this anchor while preserving the global 1.4x gate for stable floors.

  report written to sdd/plans/202604/perf_artifacts/rust_backend_phase7_floor_check.json

Phase 7E floor check passed.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
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
[core-floor-probe] stale_actionable: sase-core-rs==0.34.47 is missing 4 capability(s) that exist in a published sase-core release.
[core-floor-probe] service_enablement_resolve: first appears in sase-core fe7c4a0 (feat(service): add status snapshot wire); release v0.34.48 contains it.
[core-floor-probe] service_status_build: first appears in sase-core fe7c4a0 (feat(service): add status snapshot wire); release v0.34.48 contains it.
[core-floor-probe] service_status_read: first appears in sase-core fe7c4a0 (feat(service): add status snapshot wire); release v0.34.48 contains it.
[core-floor-probe] service_status_write: first appears in sase-core fe7c4a0 (feat(service): add status snapshot wire); release v0.34.48 contains it.
{"cache_hit": true, "capabilities": [{"commit": "fe7c4a0", "name": "service_enablement_resolve", "release": "v0.34.48", "subject": "feat(service): add status snapshot wire"}, {"commit": "fe7c4a0", "name": "service_status_build", "release": "v0.34.48", "subject": "feat(service): add status snapshot wire"}, {"commit": "fe7c4a0", "name": "service_status_read", "release": "v0.34.48", "subject": "feat(service): add status snapshot wire"}, {"commit": "fe7c4a0", "name": "service_status_write", "release": "v0.34.48", "subject": "feat(service): add status snapshot wire"}], "declared_floor": "0.34.47", "exit_code": 3, "message": "sase-core-rs==0.34.47 is missing 4 capability(s) that exist in a published sase-core release.", "status": "stale_actionable"}
✓ committed plans
✗ test cost
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-cost                │
└───────────────────────────────────────────────────────┘

---------- Running pytest cost attribution lane... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 12/12 workers
12 workers [42710 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
....................s................................................... [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
.................................................s...................... [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................s............................... [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
.......................................................s................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
..........................................s............................. [ 23%]
.....................................s.....s............................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 32%]
s....................................................................... [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
.........................................s.......s....s........s........ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 50%]
........................................................................ [ 50%]
.....................................................s.................. [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
.............s.......................................................... [ 58%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
..............                                                           [100%]/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while calling GC callback <function gc_cumulative_time.<locals>.gc_callback at 0x7f69b70cfd70>: None

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/hypothesis/internal/conjecture/junkdrawer.py", line 468, in gc_callback
    now = _perf_counter()
KeyboardInterrupt


  warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: 12 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=990853) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/xprompt/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_xprompt_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_xprompt_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/test_xprompt_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=990828) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=990844) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/actions/update_toast.py:87: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Failed to start periodic update checks", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
- sase global leak detector: 0 poisoning change(s) across 0 test(s); 61911 warming mutation(s) filtered; 672 cooling mutation(s) filtered; 2728 invalidation(s) filtered; report=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-global-leaks.json -
============================= slowest 20 durations =============================
64.09s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
53.05s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
51.72s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
42.57s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
41.36s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
27.86s call     tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess
26.73s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
23.00s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
19.14s call     tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_opens_preview_modal
17.40s call     tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
16.94s call     tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py::test_updates_pane_skipped_editables_with_wheel_core_open_mixed_preview
16.75s call     tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py::test_updates_pane_mixed_core_only_success_restarts_once_and_receipts
16.70s call     tests/ace/tui/test_plugins_browser_pane_marks.py::test_plugin_mark_survives_scope_switch_and_is_consumed_by_install
15.41s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
15.36s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
11.42s call     tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_flag_on_relaunches_stranded_agent
10.28s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
10.15s call     tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds
9.58s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
9.48s call     tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
========= 42696 passed, 15 skipped, 92 warnings in 1708.15s (0:28:28) ==========
recording: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260918T065242Z-990654.json
baseline:  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/perf/baselines/test_cost_baseline.json
timings:   /home/bryan/.sase/test-selection/gh_sase-org__sase/timings covers 554/3963 files total=935.137s cost-delta=+4960.311s (+530.4%)
Test Cost Report
  record: c7e9ded2d9953035
  recorded_at: 2026-09-18T06:52:42.512820+00:00
  host: athena
  mode: cost
  worker_count: 12

Summary
  per-test wall: 5895.449s
  per-test CPU: 3485.806s
  per-test idle: 2409.643s
  collection: 327.400s
  worker wall: 21910.367s
  worker CPU: 17822.022s
  peak worker RSS KiB: 1,969,960 KiB
  median worker RSS KiB: 782,808 KiB
  post-collection worker RSS KiB: 782,904 KiB
  worker RSS curve: start=187,196 KiB, post_collection=782,904 KiB, median=782,808 KiB, peak=1,969,960 KiB, samples=460
  files: 3963
  nodes: 42710

Diff
  per-test wall: current 5895.449s; baseline 3719.000s; delta +2176.449 (+58.5%)
  per-test CPU: current 3485.806s; baseline n/a; delta n/a
  per-test idle: current 2409.643s; baseline n/a; delta n/a
  collection: current 327.400s; baseline 27.600s; delta +299.800 (+1086.2%)
  worker wall: current 21910.367s; baseline n/a; delta n/a
  worker CPU: current 17822.022s; baseline n/a; delta n/a
  peak worker RSS KiB: current 1,969,960 KiB; baseline 1,126,400 KiB; delta +843560.000 (+74.9%)
  median worker RSS KiB: current 782,808 KiB; baseline n/a; delta n/a
  post-collection worker RSS KiB: current 782,904 KiB; baseline n/a; delta n/a

Causes
  AcePage.__aenter__: 1150.419s (779x)  delta +760.419 (+195.0%)
  Textual App.run_test enter: 899.859s (4011x)  delta +477.859 (+113.2%)
  ACE settle_pilot: 562.400s (8815x)  delta n/a
  subprocess.run: 541.327s (50955x)  delta +281.327 (+108.2%)
  Pilot.pause(delay): 462.180s (18019x)  delta n/a
  sase.config.core.load_merged_config: 183.777s (30025x)  delta +183.777
  Textual App.run_test exit: 87.812s (4011x)  delta n/a
  sase.main.parser.create_parser: 74.737s (2013x)  delta +14.737 (+24.6%)
  AcePage.__aexit__: 71.447s (777x)  delta n/a
  Pilot.pause(None): 50.535s (836x)  delta n/a
  YAML load: 26.057s (59944x)  delta -38.943 (-59.9%)
  subprocess.Popen: 0.895s (1121x)  delta n/a
  ACE pause_until_cpu_idle: 0.001s (2x)  delta n/a
  gettext.find: 0.001s (10x)  delta +0.001

Top 10 Files
  by wall:
     105.030s  tests/test_check_feature_flags_tool_run.py
      89.246s  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      74.503s  tests/fakey/test_monitor_capacity_e2e.py
      59.963s  tests/test_ace_testing.py
      54.297s  tests/ace/tui/test_plugins_browser_pane_loading.py
      48.832s  tests/ace/tui/test_axe_entry_editor_modal.py
      46.007s  tests/ace/tui/test_agents_filter_bar_session.py
      44.830s  tests/history/test_continuation_replay_hydration.py
      42.598s  tests/test_contract_manifest.py
      42.213s  tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py
  by CPU:
     104.822s  tests/test_check_feature_flags_tool_run.py
      83.077s  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      59.964s  tests/test_ace_testing.py
      50.469s  tests/ace/tui/test_plugins_browser_pane_loading.py
      44.869s  tests/ace/tui/test_axe_entry_editor_modal.py
      38.890s  tests/ace/tui/test_usage_header.py
      37.654s  tests/ace/tui/test_artifacts_scaffold.py
      34.669s  tests/ace/tui/test_plugins_browser_pane_install.py
      34.563s  tests/ace/tui/test_agents_filter_bar_session.py
      34.020s  tests/ace/tui/test_xprompt_browser_load_keymap.py
  by idle:
      68.064s  tests/fakey/test_monitor_capacity_e2e.py
      42.565s  tests/test_contract_manifest.py
      32.785s  tests/history/test_continuation_replay_hydration.py
      31.876s  tests/test_procs_service.py
      30.647s  tests/monitor/test_monitor_start_ack.py
      29.556s  tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py
      28.183s  tests/pager/test_rendered_link_contract.py
      27.868s  tests/sdd/test_git_identity_fixture.py
      27.422s  tests/ace/tui/test_agents_zoom_panel_files.py
      22.418s  tests/llm_provider/test_grok_usage_probe.py
  by AcePage.__aenter__:
      52.386s    37x  tests/test_ace_testing.py
      29.968s    21x  tests/ace/tui/test_usage_header.py
      26.408s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
      24.711s    15x  tests/ace/tui/test_artifacts_current_project_scope.py
      23.836s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
      22.367s    15x  tests/test_keymaps_e2e.py
      22.202s    13x  tests/ace/tui/test_statistics_view_number_select.py
      21.415s    17x  tests/ace/tui/test_axe_entry_editor_modal.py
      21.223s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
      19.688s    12x  tests/ace/tui/test_artifacts_patches_navigator.py
  by Textual App.run_test enter:
      35.834s    40x  tests/test_ace_testing.py
      20.792s    21x  tests/ace/tui/test_usage_header.py
      16.597s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
      16.429s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
      15.996s    15x  tests/test_keymaps_e2e.py
      13.445s    17x  tests/ace/tui/test_axe_entry_editor_modal.py
      13.275s     9x  tests/ace/tui/test_plugins_browser_pane_scopes.py
      12.007s     9x  tests/ace/tui/test_config_center_alternate_tab.py
      12.002s    13x  tests/ace/tui/test_statistics_view_number_select.py
      11.983s    15x  tests/ace/tui/test_artifacts_current_project_scope.py
  by ACE settle_pilot:
      35.598s    21x  tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py
      31.625s   143x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      21.217s    23x  tests/ace/tui/test_plugins_browser_pane_marks.py
      19.590s    30x  tests/ace/tui/test_plugins_browser_pane_uninstall.py
      17.132s    88x  tests/ace/tui/test_plugins_browser_pane_loading.py
      14.050s    36x  tests/ace/tui/test_config_pane_widget_commit.py
      12.086s    54x  tests/ace/tui/test_axe_entry_editor_modal.py
      10.423s    35x  tests/ace/tui/test_config_pane_widget_jump.py
       8.538s   272x  tests/ace/tui/test_agents_filter_bar_session.py
       8.120s    36x  tests/ace/tui/test_plugins_browser_pane_update.py
  by subprocess.run:
      42.566s     1x  tests/test_contract_manifest.py
      27.870s     6x  tests/sdd/test_git_identity_fixture.py
      16.910s     8x  tests/monitor/test_monitor_supervise_timeout.py
      15.099s    25x  tests/test_commit_workflow_bead_lifecycle_e2e.py
      14.630s    18x  tests/test_plan_approval_responses.py
      11.741s    14x  tests/test_plan_gates_execution.py
       9.558s    11x  tests/test_bead/test_snooze_gate_actions.py
       8.194s    10x  tests/test_plan_gates_action_api.py
       7.668s     9x  tests/test_bead/test_flag_gate.py
       7.517s     9x  tests/ace/tui/test_notification_plan_gate.py
  by Pilot.pause(delay):
      26.665s   286x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      20.675s   204x  tests/pager/test_rendered_link_contract.py
      15.693s   176x  tests/ace/tui/test_plugins_browser_pane_loading.py
      10.577s    72x  tests/ace/tui/test_config_pane_widget_commit.py
      10.478s   108x  tests/ace/tui/test_axe_entry_editor_modal.py
       9.831s    70x  tests/ace/tui/test_config_pane_widget_jump.py
       7.548s    86x  tests/ace/tui/test_xprompt_browser_load_keymap.py
       7.541s   544x  tests/ace/tui/test_agents_filter_bar_session.py
       7.524s    64x  tests/ace/tui/test_config_pane_widget.py
       6.930s    80x  tests/ace/tui/test_feature_flags_pane.py
  by sase.config.core.load_merged_config:
       2.716s    49x  tests/ace/tui/test_plugins_browser_pane_jump.py
       1.958s   453x  tests/test_bead/test_cli_show_style.py
       1.819s    71x  tests/test_bead/test_cli_show_multi.py
       0.865s    44x  tests/test_bead/test_cli_golden.py
       0.746s    80x  tests/completion/test_build.py
       0.698s   199x  tests/test_ace_testing.py
       0.669s    23x  tests/test_plan_search_cli.py
       0.578s    23x  tests/test_plan_validate_diagnostics.py
       0.574s   105x  tests/ace/tui/test_usage_header.py
       0.570s    17x  tests/ace/tui/modals/test_input_collection_modal.py
  by Textual App.run_test exit:
       3.919s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
       3.150s     3x  tests/ace/tui/test_artifacts_files_grouping.py
       2.765s    17x  tests/ace/tui/test_axe_entry_editor_modal.py
       2.625s    13x  tests/ace/tui/test_statistics_view_number_select.py
       2.355s    10x  tests/ace/tui/test_plugins_browser_pane_agent_clis.py
       2.330s     8x  tests/ace/tui/test_statistics_pane_filters.py
       1.698s    13x  tests/ace/tui/test_xprompt_browser_load_keymap.py
       1.669s     9x  tests/ace/tui/test_config_pane_widget.py
       1.611s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
       1.483s    10x  tests/ace/tui/test_help_modal_filter.py
  by sase.main.parser.create_parser:
       2.539s   146x  tests/test_bead/test_cli_show_style.py
       2.511s    21x  tests/main/test_parser_proc.py
       2.339s    13x  tests/test_bead/test_cli_show_multi.py
       2.000s    50x  tests/completion/test_update_refresh_soak.py
       1.923s     7x  tests/test_bead/test_claimed_status.py
       1.887s     6x  tests/test_bead/test_cli_close_gate_settle.py
       1.840s     9x  tests/main/test_memory_parser_handler.py
       1.756s     8x  tests/main/test_notify_parser.py
       1.746s    15x  tests/test_bead/test_task_type_create.py
       1.653s    20x  tests/completion/test_build.py
  by AcePage.__aexit__:
       4.105s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
       3.229s     3x  tests/ace/tui/test_artifacts_files_grouping.py
       2.776s    17x  tests/ace/tui/test_axe_entry_editor_modal.py
       2.631s    13x  tests/ace/tui/test_statistics_view_number_select.py
       2.440s    10x  tests/ace/tui/test_plugins_browser_pane_agent_clis.py
       2.334s     8x  tests/ace/tui/test_statistics_pane_filters.py
       1.857s     9x  tests/ace/tui/test_config_pane_widget.py
       1.745s    13x  tests/ace/tui/test_xprompt_browser_load_keymap.py
       1.678s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
       1.505s     7x  tests/ace/tui/test_plugins_browser_pane_marks.py
  by Pilot.pause(None):
       4.396s    39x  tests/test_notification_modal_scroll.py
       3.362s    67x  tests/test_models_panel_selector_builder.py
       3.210s    36x  tests/test_command_palette_modal.py
       3.112s    44x  tests/test_models_panel_override_flows.py
       2.761s    12x  tests/test_models_panel_runner_limit.py
       2.446s    39x  tests/test_models_panel_jump.py
       2.063s    29x  tests/test_models_panel_edit.py
       2.054s    44x  tests/test_approve_options_modal_state.py
       1.739s    25x  tests/test_models_panel_edit_custom.py
       1.657s    32x  tests/test_model_picker_modal.py
  by YAML load:
       3.791s  5328x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
       1.259s  5171x  tests/main/test_init_skills_sources.py
       0.864s   959x  tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py
       0.768s   980x  tests/test_bead_xprompt_tags.py
       0.717s  3426x  tests/main/test_init_memory_task_types_note.py
       0.490s  2382x  tests/main/test_init_memory_plan.py
       0.485s  1632x  tests/test_bead/test_work_queue_capacity.py
       0.433s  2112x  tests/main/test_init_memory_commit.py
       0.411s     5x  tests/test_config_schema_ace.py
       0.404s     6x  tests/test_models_panel_keymaps.py
  by subprocess.Popen:
       0.108s     2x  tests/test_agent_name_wipe.py
       0.047s    67x  tests/test_xprompt_model_alias_shortcut_parity.py
       0.031s    34x  tests/test_procs_service.py
       0.028s    49x  tests/sdd_store/test_sidecar_bead_adoption.py
       0.024s    33x  tests/test_xprompt_directive_completion_parity.py
       0.022s    38x  tests/sdd_store/test_materialize.py
       0.018s    26x  tests/llm_provider/test_grok_usage_probe.py
       0.016s    29x  tests/test_bead/test_workspace_sidecar_bead_eviction.py
       0.014s    21x  tests/llm_provider/test_codex_usage_probe.py
       0.012s    18x  tests/sdd/test_artifact_link_machine_store.py
  by ACE pause_until_cpu_idle:
       0.001s     1x  tests/test_ace_wait.py
       0.000s     1x  tests/test_a.py
  by gettext.find:
       0.000s     1x  tests/test_bead/test_cli_search.py
       0.000s     1x  tests/fakey/test_gate_capacity_custom_e2e.py
       0.000s     1x  tests/main/test_proc_handler_list.py
       0.000s     1x  tests/test_mobile_gateway.py
       0.000s     1x  tests/test_typecheck_extensionless_tools_tool.py
       0.000s     1x  tests/ace/tui/artifact_file_viewer/test_entrypoint.py
       0.000s     1x  tests/agent_clis/test_cli.py
       0.000s     1x  tests/test_agent_restart_cli.py
       0.000s     1x  tests/test_plugin_cli_show.py
       0.000s     1x  tests/test_core_health.py
test cost budget regression: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260918T065242Z-990654.json
budgets: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/perf/baselines/test_cost_budgets.json
- [hard] causes.ace_page_enter.cpu: actual 1153.732 exceeds budget 910.000 + 25% tolerance (1137.500)
- [hard] causes.textual_app_run_test_enter.cpu: actual 902.826 exceeds budget 720.000 + 25% tolerance (900.000)
test cost budget advisories: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260918T065242Z-990654.json
wall-clock overages usually mean the host was busy, not that the suite got more expensive; the cpu/count figures alongside each entry are contention-stable, so compare them to tell the two apart.
- [advisory] total_file_wall_seconds: actual 5895.449 exceeds budget 4700.000 + 15% tolerance (5405.000) (cpu=3485.806s)
- [advisory] causes.ace_page_enter: actual 1150.419 exceeds budget 540.000 + 15% tolerance (621.000) (cpu=1153.732s, count=779)
- [advisory] causes.ace_settle_pilot: actual 562.400 exceeds budget 340.000 + 15% tolerance (391.000) (cpu=498.042s, count=8815)
- [advisory] causes.parser_create: actual 74.737 exceeds budget 52.000 + 15% tolerance (59.800) (cpu=74.628s, count=2013)
- [advisory] causes.pilot_pause_delay: actual 462.180 exceeds budget 230.000 + 15% tolerance (264.500) (cpu=426.824s, count=18019)
- [advisory] causes.textual_app_run_test_enter: actual 899.859 exceeds budget 470.000 + 15% tolerance (540.500) (cpu=902.826s, count=4011)
- [advisory] causes.yaml_load: actual 26.057 exceeds budget 20.000 + 15% tolerance (23.000) (cpu=26.032s, count=59944)
error: recipe `test-cost` failed on line 456 with exit code 1
error: recipe `check-full` failed on line 718 with exit code 1

