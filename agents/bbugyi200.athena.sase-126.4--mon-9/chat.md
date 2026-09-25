# Chat History - ace-run (sase-126.4--mon-9)

- **TIMESTAMP:** 2026-09-18 01:57:19 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-126.4--mon-9

## Prompt

sase monitor start --command 'just install && just fix && just check && just test-visual && just phase7-perf-check && just check-full' --reason 'Run integrated verification for bead sase-126.4 after accepting the artifacts split narrow key-legend visual golden'

## Response

[install] Installing local sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/linked/sase-core for local dev.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-wheels/db4ece99d0947094d80d77f1048f98580a1317c29229d7be540fdd21777fb7c3/sase_core_rs-0.34.50-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 1ms
Prepared 1 package in 0.16ms
Uninstalled 1 package in 0.87ms
Installed 1 package in 7ms
 ~ sase-core-rs==0.34.50 (from file:///home/bryan/.sase/cache/sase-core-wheels/db4ece99d0947094d80d77f1048f98580a1317c29229d7be540fdd21777fb7c3/sase_core_rs-0.34.50-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
    Finished `dev-update` profile [optimized] target(s) in 0.14s
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/sase-xprompt-lsp
uv pip install --python .venv/bin/python --no-sources $(just _core-overrides-arg) -e ".[dev]"
Resolved 97 packages in 189ms
   Building sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
      Built sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10
Prepared 1 package in 476ms
Uninstalled 1 package in 2ms
Installed 1 package in 4ms
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
AGENTS.md 94ms (unchanged)
CLAUDE.md 55ms (unchanged)
CONTRIBUTING.md 8ms (unchanged)
demos/README.md 43ms (unchanged)
demos/tapes/AGENTS.md 2ms (unchanged)
demos/tapes/CLAUDE.md 2ms (unchanged)
demos/tapes/GEMINI.md 2ms (unchanged)
demos/tapes/OPENCODE.md 2ms (unchanged)
demos/tapes/QWEN.md 2ms (unchanged)
docs/ace.md 1673ms (unchanged)
docs/acknowledgements.md 22ms (unchanged)
docs/agent_families.md 94ms (unchanged)
docs/agent_images.md 101ms (unchanged)
docs/agent_providers.md 43ms (unchanged)
docs/agents_sidecar.md 54ms (unchanged)
docs/architecture.md 38ms (unchanged)
docs/artifact_links.md 37ms (unchanged)
docs/artifact_references.md 41ms (unchanged)
docs/artifacts_pane_contract.md 27ms (unchanged)
docs/artifacts_pane_visual_grammar.md 40ms (unchanged)
docs/axe.md 226ms (unchanged)
docs/beads.md 292ms (unchanged)
docs/blog/index.md 3ms (unchanged)
docs/blog/posts/axe-background-daemon.md 26ms (unchanged)
docs/blog/posts/beads-and-sdd.md 27ms (unchanged)
docs/blog/posts/changespecs-in-practice.md 24ms (unchanged)
docs/blog/posts/commit-workflows-plugins.md 26ms (unchanged)
docs/blog/posts/hello-sase-your-first-15-minutes.md 30ms (unchanged)
docs/blog/posts/prompt-widget-and-nvim.md 31ms (unchanged)
docs/blog/posts/structured-agentic-software-engineering.md 49ms (unchanged)
docs/blog/posts/telegram-mobile-agents.md 25ms (unchanged)
docs/blog/posts/whats-next-memory-mobile-web.md 16ms (unchanged)
docs/blog/posts/why-coding-agents-need-orchestration.md 80ms (unchanged)
docs/blog/posts/xprompts-in-depth.md 28ms (unchanged)
docs/change_spec.md 33ms (unchanged)
docs/cli.md 157ms (unchanged)
docs/commit_workflows.md 110ms (unchanged)
docs/completion.md 36ms (unchanged)
docs/configuration.md 1375ms (unchanged)
docs/content_layout.md 13ms (unchanged)
docs/development.md 155ms (unchanged)
docs/editor.md 104ms (unchanged)
docs/fakey.md 14ms (unchanged)
docs/getting_started.md 43ms (unchanged)
docs/images/blog/one_prompt_provider_clis.prompt.md 9ms (unchanged)
docs/images/blog/prompt_burrito.prompt.md 7ms (unchanged)
docs/images/blog/window_farm_vs_control_tower.prompt.md 6ms (unchanged)
docs/images/commit-workflow-infographic.critique.md 21ms (unchanged)
docs/images/commit-workflow-infographic.prompt.md 15ms (unchanged)
docs/images/infographic-style-brief.md 21ms (unchanged)
docs/images/rust-backend-boundary-infographic.critique.md 31ms (unchanged)
docs/images/rust-backend-boundary-infographic.prompt.md 5ms (unchanged)
docs/images/sase_overview.critique.md 6ms (unchanged)
docs/images/sase_overview.prompt.md 6ms (unchanged)
docs/images/sase_tui_tabs_infographic.critique.md 29ms (unchanged)
docs/images/sase_tui_tabs_infographic.prompt.md 4ms (unchanged)
docs/images/sase-rust-core-integration.critique.md 28ms (unchanged)
docs/images/sase-rust-core-integration.prompt.md 3ms (unchanged)
docs/images/sase-telegram-integration.critique.md 22ms (unchanged)
docs/images/sase-telegram-integration.prompt.md 9ms (unchanged)
docs/images/workflow-execution-infographic.critique.md 47ms (unchanged)
docs/images/workflow-execution-infographic.prompt.md 8ms (unchanged)
docs/images/xprompt-resolution-infographic.critique.md 7ms (unchanged)
docs/images/xprompt-resolution-infographic.prompt.md 10ms (unchanged)
docs/images/zorg-zettel-vision-infographic.critique.md 35ms (unchanged)
docs/index.md 5ms (unchanged)
docs/init.md 66ms (unchanged)
docs/integrations.md 33ms (unchanged)
docs/llms.md 386ms (unchanged)
docs/memory.md 43ms (unchanged)
docs/mentors.md 31ms (unchanged)
docs/mobile_gateway.md 48ms (unchanged)
docs/mobile_mvp_runbook.md 32ms (unchanged)
docs/monitors.md 89ms (unchanged)
docs/notifications.md 232ms (unchanged)
docs/pager.md 32ms (unchanged)
docs/perf_runbook.md 106ms (unchanged)
docs/plugins.md 126ms (unchanged)
docs/project_spec.md 34ms (unchanged)
docs/prompt.md 28ms (unchanged)
docs/query_language.md 23ms (unchanged)
docs/remote_dispatch.md 28ms (unchanged)
docs/rust_backend.md 93ms (unchanged)
docs/sdd_storage.md 38ms (unchanged)
docs/sdd.md 87ms (unchanged)
docs/sudo.md 31ms (unchanged)
docs/telemetry.md 32ms (unchanged)
docs/troubleshooting/agent-revival.md 8ms (unchanged)
docs/troubleshooting/runner-slots.md 23ms (unchanged)
docs/vcs.md 76ms (unchanged)
docs/workflow_spec.md 100ms (unchanged)
docs/workspace.md 69ms (unchanged)
docs/xprompt.md 404ms (unchanged)
GEMINI.md 27ms (unchanged)
INSTALL.md 23ms (unchanged)
OPENCODE.md 27ms (unchanged)
QWEN.md 28ms (unchanged)
README.md 14ms (unchanged)
sase/memory/cli_rules.md 5ms (unchanged)
sase/memory/decisions.md 10ms (unchanged)
sase/memory/decisions/agents-sync-publish-only.md 8ms (unchanged)
sase/memory/decisions/ci-two-speed-split.md 7ms (unchanged)
sase/memory/decisions/corpus-before-mechanism.md 5ms (unchanged)
sase/memory/decisions/gates-never-block.md 7ms (unchanged)
sase/memory/decisions/host-owned-completion.md 5ms (unchanged)
sase/memory/decisions/memory-links-are-authored.md 5ms (unchanged)
sase/memory/decisions/memory-webs.md 7ms (unchanged)
sase/memory/decisions/record-before-admit.md 14ms (unchanged)
sase/memory/decisions/rust-core-required.md 7ms (unchanged)
sase/memory/decisions/single-turn-agents.md 7ms (unchanged)
sase/memory/decisions/two-speed-verification.md 7ms (unchanged)
sase/memory/decisions/v1-import-retired.md 10ms (unchanged)
sase/memory/decisions/webs-render-in-their-own-section.md 8ms (unchanged)
sase/memory/generated_skills.md 10ms (unchanged)
sase/memory/glossary.md 5ms (unchanged)
sase/memory/glossary/agent-clan.md 2ms (unchanged)
sase/memory/glossary/agent-family.md 2ms (unchanged)
sase/memory/glossary/agent-hood.md 2ms (unchanged)
sase/memory/glossary/agent-instruction-file.md 3ms (unchanged)
sase/memory/glossary/agent-neighbor.md 2ms (unchanged)
sase/memory/glossary/agent-node.md 2ms (unchanged)
sase/memory/glossary/agent-shell.md 2ms (unchanged)
sase/memory/glossary/agent-tribe.md 2ms (unchanged)
sase/memory/glossary/artifact-markdown-file.md 3ms (unchanged)
sase/memory/glossary/artifact-reference.md 2ms (unchanged)
sase/memory/glossary/artifact.md 2ms (unchanged)
sase/memory/glossary/chop.md 2ms (unchanged)
sase/memory/glossary/core-memory.md 2ms (unchanged)
sase/memory/glossary/current-project.md 2ms (unchanged)
sase/memory/glossary/feature-flag.md 2ms (unchanged)
sase/memory/glossary/flag-bead.md 3ms (unchanged)
sase/memory/glossary/gate-shell.md 3ms (unchanged)
sase/memory/glossary/lumberjack.md 2ms (unchanged)
sase/memory/glossary/memory-strand.md 1ms (unchanged)
sase/memory/glossary/memory-web.md 2ms (unchanged)
sase/memory/glossary/patch.md 2ms (unchanged)
sase/memory/glossary/proc-shell.md 2ms (unchanged)
sase/memory/glossary/proc.md 3ms (unchanged)
sase/memory/glossary/reference-memory.md 2ms (unchanged)
sase/memory/glossary/required-plugin.md 3ms (unchanged)
sase/memory/glossary/sase-agent.md 2ms (unchanged)
sase/memory/glossary/sase-gate.md 5ms (unchanged)
sase/memory/glossary/sase-monitor.md 3ms (unchanged)
sase/memory/glossary/sase-node.md 3ms (unchanged)
sase/memory/glossary/sase-project.md 3ms (unchanged)
sase/memory/glossary/sase-repo.md 2ms (unchanged)
sase/memory/glossary/sase-shell.md 2ms (unchanged)
sase/memory/glossary/sase-workspace.md 2ms (unchanged)
sase/memory/glossary/stitch.md 2ms (unchanged)
sase/memory/glossary/strand-keyword.md 2ms (unchanged)
sase/memory/glossary/task-type.md 3ms (unchanged)
sase/memory/glossary/usage-window.md 3ms (unchanged)
sase/memory/glossary/xprompt-memory.md 2ms (unchanged)
sase/memory/glossary/xprompt-part.md 1ms (unchanged)
sase/memory/glossary/xprompt-swarm.md 2ms (unchanged)
sase/memory/glossary/xprompt-workflow.md 2ms (unchanged)
sase/memory/glossary/xprompt.md 2ms (unchanged)
sase/memory/gotchas.md 2ms (unchanged)
sase/memory/lint_and_test.md 8ms (unchanged)
sase/memory/README.md 33ms (unchanged)
sase/memory/rust_core_backend_boundary.md 4ms (unchanged)
sase/memory/sase_artifacts.md 12ms (unchanged)
sase/memory/sase_beads.md 22ms (unchanged)
sase/memory/sase_flags.md 14ms (unchanged)
sase/memory/sase_sizes.md 7ms (unchanged)
sase/memory/sase.md 15ms (unchanged)
sase/memory/symvision.md 21ms (unchanged)
sase/memory/task_types.md 6ms (unchanged)
sase/memory/task_types/bug.md 6ms (unchanged)
sase/memory/task_types/ci.md 7ms (unchanged)
sase/memory/task_types/feature.md 7ms (unchanged)
sase/memory/task_types/flake.md 9ms (unchanged)
sase/memory/task_types/memory.md 8ms (unchanged)
sase/memory/tui_perf.md 20ms (unchanged)
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
src/sase/memory/assets/memory-directory-map.prompt.md 7ms (unchanged)
src/sase/sdd/assets/agents-directory-map.png.prompt.md 7ms (unchanged)
src/sase/sdd/assets/beads-directory-map.png.prompt.md 6ms (unchanged)
src/sase/sdd/assets/plans-directory-map.png.prompt.md 6ms (unchanged)
src/sase/sdd/assets/research-directory-map.png.prompt.md 5ms (unchanged)
src/sase/xprompts/coder.md 2ms (unchanged)
src/sase/xprompts/fix_hook.md 3ms (unchanged)
src/sase/xprompts/skills/sase_agents_status.md 12ms (unchanged)
src/sase/xprompts/skills/sase_chats.md 12ms (unchanged)
src/sase/xprompts/skills/sase_final.md 13ms (unchanged)
src/sase/xprompts/skills/sase_gate.md 49ms (unchanged)
src/sase/xprompts/skills/sase_git_commit.md 20ms (unchanged)
src/sase/xprompts/skills/sase_memory_read.md 7ms (unchanged)
src/sase/xprompts/skills/sase_memory_write.md 12ms (unchanged)
src/sase/xprompts/skills/sase_monitor.md 18ms (unchanged)
src/sase/xprompts/skills/sase_new_task.md 12ms (unchanged)
src/sase/xprompts/skills/sase_notify.md 9ms (unchanged)
src/sase/xprompts/skills/sase_patches.md 13ms (unchanged)
src/sase/xprompts/skills/sase_pipe.md 7ms (unchanged)
src/sase/xprompts/skills/sase_plan.md 7ms (unchanged)
src/sase/xprompts/skills/sase_project.md 5ms (unchanged)
src/sase/xprompts/skills/sase_questions.md 6ms (unchanged)
src/sase/xprompts/skills/sase_repo.md 8ms (unchanged)
src/sase/xprompts/skills/sase_run.md 20ms (unchanged)
src/sase/xprompts/skills/sase_sudo.md 7ms (unchanged)
src/sase/xprompts/skills/sase_var.md 8ms (unchanged)
src/sase/xprompts/skills/SKILL.frame.template.md 1ms (unchanged)
src/sase/xprompts/split_file.md 1ms (unchanged)
src/sase/xprompts/summarize.md 2ms (unchanged)
src/sase/xprompts/t.md 1ms (unchanged)
src/sase/xprompts/tribe.md 1ms (unchanged)
tests/ace/tui/artifacts_contract/fixtures/notes/hello__a.md 2ms (unchanged)
tests/ace/tui/artifacts_contract/fixtures/notes/hello.md 2ms (unchanged)
tests/ace/tui/repro/README.md 4ms (unchanged)
tests/fixtures/agy/README.md 2ms (unchanged)
tests/fixtures/codex_stream/README.md 2ms (unchanged)
tests/fixtures/qwen_stream/README.md 1ms (unchanged)
tests/perf/README.md 16ms (unchanged)
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
scoped: selected 480 of 3972 test files (12.1%; rules: context-baseline-stale, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); contexts baseline stale; est 871s/444s; gear 4 workers
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
created: 14/14 workers
14 workers [960 items]

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
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
27.80s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_sase_context.py::test_agents_phase_family_bead_and_plan_context_png_snapshot
14.83s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot
13.74s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_parked_png_snapshot
13.55s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_weighted_runner_capacity_png_snapshots
12.88s call     tests/ace/tui/visual/test_ace_png_snapshots_agents.py::test_runner_slot_queue_window_png_snapshot
12.87s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_g_prefix_hints_png_snapshot
12.71s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_tribe_panel.py::test_tribe_panel_four_level_png_snapshots
12.39s call     tests/ace/tui/visual/test_ace_png_snapshots_placeholder_completion.py::test_placeholder_completion_panel_png_snapshot
12.24s call     tests/ace/tui/visual/test_ace_png_snapshots_agents_zoom_context.py::test_agents_context_zoom_modal_png_snapshot
12.19s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_submit_choice_modal_png_snapshot
12.14s call     tests/ace/tui/visual/test_ace_png_snapshots_xprompt_arg_completion.py::test_xprompt_arg_name_completion_png_snapshot[dark]
11.83s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_dirty_png_snapshot
11.63s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_ordered_highlight_solo_png_snapshot[textual-dark-prompt_ordered_highlight_solo_dark_120x40-ACE prompt input \u2014 ordered-marker highlighting, dark theme]
11.63s call     tests/ace/tui/visual/test_ace_png_snapshots_model_alias_completion.py::test_model_alias_completion_full_menu_png_snapshot[textual-light-prompt_model_alias_completion_full_light_120x40-ACE prompt input \u2014 equals alias completion full menu, light theme]
11.46s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_codeblock_highlight_solo_png_snapshot[textual-light-prompt_codeblock_highlight_solo_light_120x40-ACE prompt input \u2014 code highlighting, light theme]
11.45s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_search_count_pill_png_snapshot[textual-light-prompt_search_count_pill_light_120x40-ACE prompt input - committed search count pill, light theme]
11.44s call     tests/ace/tui/visual/test_ace_png_snapshots_mini_xprompt.py::test_mini_xprompt_pane_dirty_png_snapshot
11.40s call     tests/ace/tui/visual/test_ace_png_snapshots_finalizer_completion.py::test_finalizer_completion_mixed_menu_png_snapshot
11.21s call     tests/ace/tui/visual/test_ace_png_snapshots_model_explicit_completion.py::test_model_explicit_completion_full_menu_png_snapshot[dark]
11.21s call     tests/ace/tui/visual/test_ace_png_snapshots_prompt_stack.py::test_prompt_stack_snippet_new_png_snapshot
=========== 960 passed, 1 skipped, 14 warnings in 253.59s (0:04:13) ============
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
  python_direct           0.124        0.128      0.142      0.148
  rust_direct             0.042        0.043      0.045      0.047
  rust_facade             0.069        0.072      0.077      0.077

# synthetic_200_specs (118008 bytes)
  runs=15 warmup=3
  rust_available=True
  scenario               min_ms    median_ms     p95_ms     max_ms
  ----------------------------------------------------------------
  python_direct          12.767       12.988     13.184     13.193
  rust_direct             4.532        4.673      5.030      5.133
  rust_facade             6.613        7.250      8.136      8.366

==== Phase 7E floor: bench_core_query ====

# parse_only
  query='"feature" OR status:Ready'
  scenario                         min_ms    median_ms     p95_ms     max_ms
  --------------------------------------------------------------------------
  python_direct_parse               0.009        0.009      0.012      0.012
  python_facade_parse               0.024        0.024      0.027      0.040
  rust_direct_parse                 0.006        0.006      0.006      0.007
  rust_facade_parse                 0.024        0.024      0.027      0.028

# synthetic_100_specs (100 specs)
  query='"feature" OR status:Ready'
  scenario                         min_ms    median_ms     p95_ms     max_ms
  --------------------------------------------------------------------------
  python_direct_parse               0.009        0.009      0.010      0.010
  python_facade_parse               0.024        0.024      0.028      0.030
  python_parse_and_evaluate         0.425        0.435      0.445      0.458
  reference_python_batch_evaluate_many      0.429        0.440      0.455      0.459
  rust_one_shot_diagnostic_evaluate_many      4.871        5.092      5.522      6.352
  rust_persistent_corpus_compile      7.265        7.660      8.219      8.778
  rust_persistent_fully_compiled_evaluate_many      0.014        0.014      0.014      0.014
  rust_persistent_query_keystroke_evaluate_many      0.016        0.016      0.023      0.023

# synthetic_1000_specs (1000 specs)
  query='"feature" OR status:Ready'
  scenario                         min_ms    median_ms     p95_ms     max_ms
  --------------------------------------------------------------------------
  python_direct_parse               0.009        0.009      0.009      0.010
  python_facade_parse               0.024        0.025      0.031      0.032
  python_parse_and_evaluate         4.013        4.170      5.252      5.436
  reference_python_batch_evaluate_many      4.382        4.899      5.909      5.995
  rust_one_shot_diagnostic_evaluate_many     49.093       51.000     55.600     55.993
  rust_persistent_corpus_compile     78.047       82.844    135.229    139.443
  rust_persistent_fully_compiled_evaluate_many      0.141        0.143      0.148      0.148
  rust_persistent_query_keystroke_evaluate_many      0.143        0.144      0.148      0.150

# home_tree [skipped]
  reason=pass --include-home-tree for local-only home-tree measurement

==== Phase 7E floor: bench_agent_scan ====

# synthetic_6p_200pp
  projects_root=/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws10-260918_010826/tmpzt6x4urw/projects
  runs=8 warmup=2 target_name='proj001_agent_0000' workflow_name='wf_0'
  scenario                                 min_ms    median_ms     p95_ms     max_ms
  ----------------------------------------------------------------------------------
  find_named_agent                          0.185        0.203      0.330      0.330
  is_workflow_complete                      0.137        0.144      0.153      0.153
  list_running_agents                       0.251        0.259      0.279      0.279
  list_all_agents                           0.236        0.240      0.245      0.245
  list_running_agents_shared_snapshot     196.030      215.128    260.770    260.770
  list_all_agents_shared_snapshot         205.332      210.851    268.356    268.356
  tui_artifact_load                         0.213        0.223      0.237      0.237
  scan_rust_to_dict                       141.648      144.751    151.834    151.834
  scan_rust_dict_to_wire                  214.076      228.973    299.257    299.257
  scan_rust_facade                        215.263      231.883    293.918    293.918
  scan_rust_capacity_facade                19.594       20.301     21.592     21.592

==== Phase 7E floor: bench_status_state_machine ====

# golden_myproj_pure (947 bytes)
  runs=200 warmup=20 target_name='beta'
  scenario                                             min_us    median_us     p95_us     max_us
  ----------------------------------------------------------------------------------------------
  is_valid_transition                                   3.477        3.516      3.657     11.001
  remove_workspace_suffix                               1.032        1.052      1.112      1.203
  read_status_from_lines                                2.705        3.006      3.056      3.186
  apply_status_update                                   3.115        3.427      3.467      3.577
  plan_status_transition                               16.331       16.561     16.842     25.699

# golden_myproj_transition (947 bytes)
  runs=5 warmup=10 target_name='beta'
  scenario                                             min_us    median_us     p95_us     max_us
  ----------------------------------------------------------------------------------------------
  transition_patch_status_wip_to_draft                585.628      588.845    607.741    607.741
  transition_patch_status_wip_to_ready                583.885      592.001    802.763    802.763

# synthetic_200_specs_pure (113918 bytes)
  runs=200 warmup=20 target_name='spec-199'
  scenario                                             min_us    median_us     p95_us     max_us
  ----------------------------------------------------------------------------------------------
  is_valid_transition                                   3.406        3.466      3.887      4.408
  remove_workspace_suffix                               1.002        1.032      1.052      1.143
  read_status_from_lines                              292.098      310.724    326.544    382.551
  apply_status_update                                 335.531      344.082    353.254    369.416
  plan_status_transition                               16.191       16.411     16.812     26.380

# synthetic_200_specs_transition (113918 bytes)
  runs=5 warmup=10 target_name='spec-199'
  scenario                                             min_us    median_us     p95_us     max_us
  ----------------------------------------------------------------------------------------------
  transition_patch_status_wip_to_draft              15104.961    15388.342  15983.218  15983.218
  transition_patch_status_wip_to_ready              16125.008    16538.679  17473.464  17473.464

==== Phase 7 floor: bench_notification_store ====

==== Phase 7E floor check results ====
  rust_slowdown_factor = 1.40x phase7b rust median
  [PASS] parse_project_bytes.golden_myproj.facade: rust=71.65us python=n/a ceiling=174.09us must_beat_python=False
        note: scenario 'facade' missing from baseline (python) summaries
  [PASS] parse_project_bytes.synthetic_200_specs.facade: rust=7250.09us python=n/a ceiling=26762.65us must_beat_python=False
        note: scenario 'facade' missing from baseline (python) summaries
  [PASS] parse_query.parse_only.direct: rust=6.24us python=9.20us ceiling=8.08us must_beat_python=True
  [PASS] evaluate_query_many.synthetic_1000_specs.persistent_query_keystroke: rust=144.25us python=4899.09us ceiling=193.44us must_beat_python=True
        note: absolute floor uses per-anchor rust_slowdown_factor 2.90x instead of global 1.40x: The Phase 7B / query-corpus capture (66.70us) is not a portable absolute baseline for this microsecond-scale product route; the same-process must_beat_python gate remains the hardware-independent contract. Eight consecutive master CI perf-floors reports (runs 32532695452, 32537985517, 32542973465, 32546975028, 32551370513, 32555295598, 32558460537, 32568874089) measured 178.28-184.36us while still beating live Python by ~29-30x, and a clean local reproduction measured 147.07us. Use a 2.90x absolute floor (~193.44us), roughly 4.9% above the worst hosted median (184.36us in run 32558460537), to cover GitHub-hosted runner heterogeneity while preserving the global 1.4x gate for stable anchors. This still fails a material regression beyond the observed hosted envelope (2x the hosted max is ~368.72us, about 1.9x the new ceiling). Revisit once hosted medians stabilize near a recaptured baseline on current GitHub runners.
  [PASS] scan_agent_artifacts.synthetic_6p_200pp.scan_facade: rust=231882.67us python=n/a ceiling=281973.47us must_beat_python=False
        note: scenario 'scan_facade' missing from baseline (python) summaries
        note: absolute floor uses per-anchor rust_slowdown_factor 2.35x instead of global 1.40x: The Phase 7B baseline (~120 ms) predates several intentional agent-scan wire-shape expansions: pending_question.json marker scanning, workspace_dir / agent-meta tag / PDF activity / image paths / workflow-relationship / epic-start fields on agent_meta and done markers. On the 6-project x 200-per-project synthetic each addition increases both serde parsing on the Rust side and per-record Python dataclass hydration. CI, not local host timing, sets this floor: master CI perf-floors runs from 2026-08-13T22:45Z through 2026-08-14T20:56Z, including CI run IDs 31838558537 and 31840230310, produced observed medians from 146.81 ms through 269.78 ms, with run 31840230310 failing the old 2.15x ceiling at 266.26 ms. Use a 2.35x absolute floor (~282 ms), roughly 4.5% above the worst observed CI median, to cover GitHub-hosted runner heterogeneity while preserving the global 1.4x gate for stable anchors. This still catches a real facade regression that pushes the current CI distribution materially beyond the observed envelope. Revisit when Python hydration is pushed across the PyO3 boundary.
  [PASS] scan_agent_artifacts.synthetic_6p_200pp.capacity_scan_facade: rust=20300.56us python=n/a ceiling=40908.14us must_beat_python=False
        note: scenario 'capacity_scan_facade' missing from baseline (python) summaries
        note: absolute floor uses per-anchor rust_slowdown_factor 2.00x instead of global 1.40x: Phase 4 (sase-za.4) capacity-only scan anchor added alongside the slot-poll-diet fix (sase-za.1/sase-za.2) that made runner-slot admission use this mode. No CI history exists yet: three back-to-back local captures on a busy shared dev host ranged 20.15-30.91 ms against a mostly-done 1,200-dir synthetic tree (1,100 done / 100 running), already a ~1.5x spread from host contention alone. Use a 2.0x absolute floor (~41 ms) on the ~20.45 ms captured median to leave detection margin once CI history accumulates; tighten in a follow-up once master perf-floors runs establish a stable envelope, mirroring how scan_facade above was tightened from CI observations.
  [PASS] notification_store.mostly_dismissed_900.notification_store_mostly_dismissed_load_snapshot: rust=57.27us python=n/a ceiling=189.00us must_beat_python=False
        note: scenario 'notification_store_mostly_dismissed_load_snapshot' missing from baseline (python) summaries
  [PASS] apply_status_update.golden_myproj_pure.apply_status_update: rust=3.43us python=n/a ceiling=8.12us must_beat_python=False
        note: scenario 'apply_status_update' missing from baseline (python) summaries
  [PASS] notification_store.synthetic_5k.notification_store_5k_load_snapshot: rust=7518.03us python=n/a ceiling=18466.00us must_beat_python=False
        note: scenario 'notification_store_5k_load_snapshot' missing from baseline (python) summaries
  [PASS] notification_store.synthetic_5k.notification_store_5k_mark_dismissed_burst: rust=75613.90us python=n/a ceiling=6811056.00us must_beat_python=False
        note: scenario 'notification_store_5k_mark_dismissed_burst' missing from baseline (python) summaries
  [PASS] notification_store.synthetic_5k.notification_store_5k_mark_all_read: rust=92933.16us python=n/a ceiling=215055.00us must_beat_python=False
        note: scenario 'notification_store_5k_mark_all_read' missing from baseline (python) summaries
        note: absolute floor uses per-anchor rust_slowdown_factor 3.00x instead of global 1.40x: This full-store read-state mutation uses the production JSONL lock/tempfile/rename write path and showed GitHub-hosted runner IO variance at 194856us with a 157549us confirmation while sibling write-heavy notification anchors were also elevated 3-4x. Typical CI medians are near 47500us, so a 3.0x Phase 7B ceiling (~215055us) still leaves roughly a 4.5x detection margin for a real regression and remains the tightest notification-store write gate.
  [PASS] notification_store.synthetic_5k.notification_store_append_plus_rewrite_concurrency: rust=597564.03us python=n/a ceiling=2717251.60us must_beat_python=False
        note: scenario 'notification_store_append_plus_rewrite_concurrency' missing from baseline (python) summaries
  [PASS] notification_store.synthetic_5k.notification_modal_dismiss_burst: rust=634216.47us python=n/a ceiling=5098492.80us must_beat_python=False
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
created: 14/14 workers
14 workers [42710 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
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
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
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
........................................................................ [ 17%]
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
........................................................................ [ 23%]
........................................................................ [ 24%]
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
..............................................s......................... [ 29%]
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
........................................................................ [ 32%]
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
....................s................................................... [ 37%]
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
.......................................................................s [ 45%]
........s..s........s................................................... [ 45%]
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
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................s............................................... [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
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
................................................................s....... [ 54%]
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
........................................................................ [ 58%]
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
...................s.................................................... [ 60%]
...............s........................................................ [ 61%]
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
..................................F..................................... [ 68%]
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
........................................................s............... [ 78%]
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
................................s....................................... [ 82%]
................s...s................................................... [ 82%]
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
..............                                                           [100%]/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while calling GC callback <function gc_cumulative_time.<locals>.gc_callback at 0x7f94cb863530>: None

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/hypothesis/internal/conjecture/junkdrawer.py", line 468, in gc_callback
    now = _perf_counter()
KeyboardInterrupt


  warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while calling GC callback <function gc_cumulative_time.<locals>.gc_callback at 0x7f3060923d70>: None

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/hypothesis/internal/conjecture/junkdrawer.py", line 468, in gc_callback
    now = _perf_counter()
KeyboardInterrupt


  warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while calling GC callback <function gc_cumulative_time.<locals>.gc_callback at 0x7f4acdb46770>: None

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/hypothesis/internal/conjecture/junkdrawer.py", line 468, in gc_callback
    now = _perf_counter()
KeyboardInterrupt


  warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
____________ test_every_literal_managed_tmpdir_bucket_has_a_horizon ____________
[gw10] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

    def test_every_literal_managed_tmpdir_bucket_has_a_horizon() -> None:
        repo_root = Path(__file__).resolve().parents[1]
        buckets: set[str] = set()
    
        for source in (repo_root / "src" / "sase").rglob("*.py"):
            text = source.read_text(encoding="utf-8")
            if "get_sase_managed_tmpdir" not in text:
                continue
            module = ast.parse(text)
            constants = _module_string_constants(module)
            for node in ast.walk(module):
                if not isinstance(node, ast.Call) or not _calls_managed_tmpdir(node):
                    continue
                if not node.args:
                    continue
                bucket = _literal_or_module_constant(node.args[0], constants)
                if bucket is not None:
                    buckets.add(bucket)
    
>       assert buckets - set(MANAGED_TMPDIR_HORIZONS) == set()
E       AssertionError: assert {'usage-probes'} == set()
E         
E         Extra items in the left set:
E         'usage-probes'
E         Use -v to get more diff

tests/test_managed_tmp_reaper.py:145: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

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

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=272502) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=272542) is multi-threaded, use of fork() may lead to deadlocks in the child.

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

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/ace/tui/actions/update_toast.py:87: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Failed to start periodic update checks", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

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

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=272542) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
- sase global leak detector: 0 poisoning change(s) across 0 test(s); 62386 warming mutation(s) filtered; 722 cooling mutation(s) filtered; 2683 invalidation(s) filtered; report=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-global-leaks.json -
============================= slowest 20 durations =============================
64.88s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
50.13s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
48.15s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
40.70s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
29.44s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
27.37s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
22.65s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
18.74s call     tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py::test_updates_pane_sase_update_dev_confirm_closes_admin_center
18.46s call     tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_confirm_executes_and_restarts
16.79s call     tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py::test_updates_pane_mixed_managed_failure_notifies_once_without_restart
16.79s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_noop_closes_without_restart
16.69s call     tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py::test_updates_pane_manual_update_reuses_load_fetches
16.10s call     tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
15.29s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
14.51s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
11.47s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
11.07s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker
10.79s call     tests/test_proc_submission_static_invariants.py::test_production_proc_writers_do_not_emit_legacy_kinds
10.50s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
9.78s call     tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
=========================== short test summary info ============================
FAILED tests/test_managed_tmp_reaper.py::test_every_literal_managed_tmpdir_bucket_has_a_horizon
==== 1 failed, 42695 passed, 15 skipped, 94 warnings in 1402.44s (0:23:22) =====
error: recipe `test-cost` failed on line 454 with exit code 1
error: recipe `check-full` failed on line 718 with exit code 1

