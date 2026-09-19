# Chat History - ace-run (sase-11l.11.5.land--mon)

- **TIMESTAMP:** 2026-09-19 07:46:18 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-11l.11.5.land--mon

## Prompt

sase monitor start --command 'just fix && just check-full && (cd sase/repos/linked/sase-core && just check)' --reason 'Parent epic sase-11l.11 requires just fix, just check-full, and sase-core just check before close'

## Response


┌───────────────────────────────────────────────────────┐
│                RUNNING: just fix                      │
└───────────────────────────────────────────────────────┘

---------- Formatting Python with ruff... ----------
.venv-format/bin/ruff format src/ tests/
9474 files left unchanged

---------- Fixing Python with ruff... ----------
.venv-format/bin/ruff check --fix src/ tests/
[1;32mAll checks passed![0m

---------- Rendering generated docs... ----------
.venv-format/bin/python tools/render_model_alias_docs

---------- Formatting Markdown with prettier... ----------
node_modules/.bin/prettier --write "**/*.md"
(node:3842287) Warning: The 'NO_COLOR' env is ignored due to the 'FORCE_COLOR' env being set.
(Use `node --trace-warnings ...` to show where the warning was created)
AGENTS.md 112ms (unchanged)
CLAUDE.md 57ms (unchanged)
CONTRIBUTING.md 7ms (unchanged)
demos/README.md 44ms (unchanged)
demos/tapes/AGENTS.md 2ms (unchanged)
demos/tapes/CLAUDE.md 2ms (unchanged)
demos/tapes/GEMINI.md 2ms (unchanged)
demos/tapes/OPENCODE.md 3ms (unchanged)
demos/tapes/QWEN.md 2ms (unchanged)
docs/ace.md 1807ms (unchanged)
docs/acknowledgements.md 20ms (unchanged)
docs/agent_families.md 99ms (unchanged)
docs/agent_images.md 132ms (unchanged)
docs/agent_providers.md 46ms (unchanged)
docs/agents_sidecar.md 60ms (unchanged)
docs/architecture.md 44ms (unchanged)
docs/artifact_links.md 39ms (unchanged)
docs/artifact_references.md 42ms (unchanged)
docs/artifacts_pane_contract.md 31ms (unchanged)
docs/artifacts_pane_visual_grammar.md 44ms (unchanged)
docs/axe.md 244ms (unchanged)
docs/beads.md 342ms (unchanged)
docs/blog/index.md 4ms (unchanged)
docs/blog/posts/axe-background-daemon.md 25ms (unchanged)
docs/blog/posts/beads-and-sdd.md 27ms (unchanged)
docs/blog/posts/changespecs-in-practice.md 24ms (unchanged)
docs/blog/posts/commit-workflows-plugins.md 26ms (unchanged)
docs/blog/posts/hello-sase-your-first-15-minutes.md 34ms (unchanged)
docs/blog/posts/prompt-widget-and-nvim.md 35ms (unchanged)
docs/blog/posts/structured-agentic-software-engineering.md 51ms (unchanged)
docs/blog/posts/telegram-mobile-agents.md 26ms (unchanged)
docs/blog/posts/whats-next-memory-mobile-web.md 15ms (unchanged)
docs/blog/posts/why-coding-agents-need-orchestration.md 74ms (unchanged)
docs/blog/posts/xprompts-in-depth.md 28ms (unchanged)
docs/change_spec.md 34ms (unchanged)
docs/cli.md 171ms (unchanged)
docs/commit_workflows.md 119ms (unchanged)
docs/completion.md 38ms (unchanged)
docs/configuration.md 1567ms (unchanged)
docs/content_layout.md 12ms (unchanged)
docs/development.md 149ms (unchanged)
docs/editor.md 66ms (unchanged)
docs/fakey.md 14ms (unchanged)
docs/getting_started.md 43ms (unchanged)
docs/images/blog/one_prompt_provider_clis.prompt.md 9ms (unchanged)
docs/images/blog/prompt_burrito.prompt.md 5ms (unchanged)
docs/images/blog/window_farm_vs_control_tower.prompt.md 6ms (unchanged)
docs/images/commit-workflow-infographic.critique.md 28ms (unchanged)
docs/images/commit-workflow-infographic.prompt.md 11ms (unchanged)
docs/images/infographic-style-brief.md 17ms (unchanged)
docs/images/rust-backend-boundary-infographic.critique.md 42ms (unchanged)
docs/images/rust-backend-boundary-infographic.prompt.md 9ms (unchanged)
docs/images/sase_overview.critique.md 14ms (unchanged)
docs/images/sase_overview.prompt.md 9ms (unchanged)
docs/images/sase_tui_tabs_infographic.critique.md 50ms (unchanged)
docs/images/sase_tui_tabs_infographic.prompt.md 7ms (unchanged)
docs/images/sase-rust-core-integration.critique.md 41ms (unchanged)
docs/images/sase-rust-core-integration.prompt.md 5ms (unchanged)
docs/images/sase-telegram-integration.critique.md 35ms (unchanged)
docs/images/sase-telegram-integration.prompt.md 14ms (unchanged)
docs/images/workflow-execution-infographic.critique.md 63ms (unchanged)
docs/images/workflow-execution-infographic.prompt.md 14ms (unchanged)
docs/images/xprompt-resolution-infographic.critique.md 10ms (unchanged)
docs/images/xprompt-resolution-infographic.prompt.md 9ms (unchanged)
docs/images/zorg-zettel-vision-infographic.critique.md 53ms (unchanged)
docs/index.md 6ms (unchanged)
docs/init.md 70ms (unchanged)
docs/integrations.md 35ms (unchanged)
docs/llms.md 405ms (unchanged)
docs/memory.md 46ms (unchanged)
docs/mentors.md 37ms (unchanged)
docs/mobile_gateway.md 51ms (unchanged)
docs/mobile_mvp_runbook.md 34ms (unchanged)
docs/monitors.md 115ms (unchanged)
docs/notifications.md 206ms (unchanged)
docs/pager.md 34ms (unchanged)
docs/perf_runbook.md 117ms (unchanged)
docs/plugins.md 95ms (unchanged)
docs/project_spec.md 43ms (unchanged)
docs/prompt.md 30ms (unchanged)
docs/query_language.md 22ms (unchanged)
docs/remote_dispatch.md 30ms (unchanged)
docs/rust_backend.md 104ms (unchanged)
docs/sdd_storage.md 41ms (unchanged)
docs/sdd.md 97ms (unchanged)
docs/sudo.md 43ms (unchanged)
docs/telemetry.md 36ms (unchanged)
docs/troubleshooting/agent-revival.md 8ms (unchanged)
docs/troubleshooting/runner-slots.md 29ms (unchanged)
docs/vcs.md 85ms (unchanged)
docs/workflow_spec.md 92ms (unchanged)
docs/workspace.md 72ms (unchanged)
docs/xprompt.md 416ms (unchanged)
GEMINI.md 34ms (unchanged)
INSTALL.md 24ms (unchanged)
OPENCODE.md 30ms (unchanged)
QWEN.md 28ms (unchanged)
README.md 16ms (unchanged)
sase/memory/cli_rules.md 5ms (unchanged)
sase/memory/decisions.md 11ms (unchanged)
sase/memory/decisions/agents-sync-publish-only.md 8ms (unchanged)
sase/memory/decisions/ci-two-speed-split.md 6ms (unchanged)
sase/memory/decisions/corpus-before-mechanism.md 5ms (unchanged)
sase/memory/decisions/gates-never-block.md 7ms (unchanged)
sase/memory/decisions/host-owned-completion.md 5ms (unchanged)
sase/memory/decisions/memory-links-are-authored.md 6ms (unchanged)
sase/memory/decisions/memory-webs.md 9ms (unchanged)
sase/memory/decisions/record-before-admit.md 7ms (unchanged)
sase/memory/decisions/rust-core-required.md 6ms (unchanged)
sase/memory/decisions/single-turn-agents.md 5ms (unchanged)
sase/memory/decisions/two-speed-verification.md 6ms (unchanged)
sase/memory/decisions/v1-import-retired.md 13ms (unchanged)
sase/memory/decisions/webs-render-in-their-own-section.md 11ms (unchanged)
sase/memory/generated_skills.md 15ms (unchanged)
sase/memory/glossary.md 7ms (unchanged)
sase/memory/glossary/agent-clan.md 3ms (unchanged)
sase/memory/glossary/agent-family.md 4ms (unchanged)
sase/memory/glossary/agent-hood.md 4ms (unchanged)
sase/memory/glossary/agent-instruction-file.md 4ms (unchanged)
sase/memory/glossary/agent-neighbor.md 3ms (unchanged)
sase/memory/glossary/agent-node.md 3ms (unchanged)
sase/memory/glossary/agent-shell.md 3ms (unchanged)
sase/memory/glossary/agent-tribe.md 3ms (unchanged)
sase/memory/glossary/artifact-markdown-file.md 4ms (unchanged)
sase/memory/glossary/artifact-reference.md 4ms (unchanged)
sase/memory/glossary/artifact.md 3ms (unchanged)
sase/memory/glossary/chop.md 3ms (unchanged)
sase/memory/glossary/core-memory.md 3ms (unchanged)
sase/memory/glossary/current-project.md 4ms (unchanged)
sase/memory/glossary/feature-flag.md 2ms (unchanged)
sase/memory/glossary/flag-bead.md 3ms (unchanged)
sase/memory/glossary/gate-shell.md 5ms (unchanged)
sase/memory/glossary/llm-calls.md 3ms (unchanged)
sase/memory/glossary/lumberjack.md 4ms (unchanged)
sase/memory/glossary/memory-strand.md 3ms (unchanged)
sase/memory/glossary/memory-web.md 3ms (unchanged)
sase/memory/glossary/patch.md 3ms (unchanged)
sase/memory/glossary/proc-shell.md 3ms (unchanged)
sase/memory/glossary/proc.md 4ms (unchanged)
sase/memory/glossary/reference-memory.md 2ms (unchanged)
sase/memory/glossary/required-plugin.md 2ms (unchanged)
sase/memory/glossary/sase-agent.md 3ms (unchanged)
sase/memory/glossary/sase-gate.md 5ms (unchanged)
sase/memory/glossary/sase-monitor.md 4ms (unchanged)
sase/memory/glossary/sase-node.md 3ms (unchanged)
sase/memory/glossary/sase-project.md 4ms (unchanged)
sase/memory/glossary/sase-repo.md 2ms (unchanged)
sase/memory/glossary/sase-shell.md 2ms (unchanged)
sase/memory/glossary/sase-workspace.md 2ms (unchanged)
sase/memory/glossary/stitch.md 2ms (unchanged)
sase/memory/glossary/strand-keyword.md 2ms (unchanged)
sase/memory/glossary/task-type.md 3ms (unchanged)
sase/memory/glossary/usage-window.md 4ms (unchanged)
sase/memory/glossary/xprompt-memory.md 3ms (unchanged)
sase/memory/glossary/xprompt-part.md 2ms (unchanged)
sase/memory/glossary/xprompt-swarm.md 3ms (unchanged)
sase/memory/glossary/xprompt-workflow.md 3ms (unchanged)
sase/memory/glossary/xprompt.md 3ms (unchanged)
sase/memory/gotchas.md 3ms (unchanged)
sase/memory/lint_and_test.md 9ms (unchanged)
sase/memory/README.md 25ms (unchanged)
sase/memory/rust_core_backend_boundary.md 3ms (unchanged)
sase/memory/sase_artifacts.md 11ms (unchanged)
sase/memory/sase_beads.md 15ms (unchanged)
sase/memory/sase_flags.md 11ms (unchanged)
sase/memory/sase_sizes.md 5ms (unchanged)
sase/memory/sase.md 9ms (unchanged)
sase/memory/symvision.md 11ms (unchanged)
sase/memory/task_types.md 4ms (unchanged)
sase/memory/task_types/bug.md 8ms (unchanged)
sase/memory/task_types/ci.md 6ms (unchanged)
sase/memory/task_types/feature.md 6ms (unchanged)
sase/memory/task_types/flake.md 6ms (unchanged)
sase/memory/task_types/memory.md 5ms (unchanged)
sase/memory/tui_perf.md 15ms (unchanged)
sase/memory/tui_screenshot.md 12ms (unchanged)
sase/memory/tui.md 2ms (unchanged)
sase/memory/xprompts.md 21ms (unchanged)
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
src/sase/sdd/assets/beads-directory-map.png.prompt.md 8ms (unchanged)
src/sase/sdd/assets/plans-directory-map.png.prompt.md 8ms (unchanged)
src/sase/sdd/assets/research-directory-map.png.prompt.md 8ms (unchanged)
src/sase/xprompts/coder.md 3ms (unchanged)
src/sase/xprompts/fix_hook.md 5ms (unchanged)
src/sase/xprompts/skills/sase_agents_status.md 16ms (unchanged)
src/sase/xprompts/skills/sase_chats.md 17ms (unchanged)
src/sase/xprompts/skills/sase_final.md 20ms (unchanged)
src/sase/xprompts/skills/sase_gate.md 52ms (unchanged)
src/sase/xprompts/skills/sase_git_commit.md 25ms (unchanged)
src/sase/xprompts/skills/sase_memory_read.md 8ms (unchanged)
src/sase/xprompts/skills/sase_memory_write.md 9ms (unchanged)
src/sase/xprompts/skills/sase_monitor.md 20ms (unchanged)
src/sase/xprompts/skills/sase_new_task.md 12ms (unchanged)
src/sase/xprompts/skills/sase_notify.md 9ms (unchanged)
src/sase/xprompts/skills/sase_patches.md 13ms (unchanged)
src/sase/xprompts/skills/sase_pipe.md 6ms (unchanged)
src/sase/xprompts/skills/sase_plan.md 7ms (unchanged)
src/sase/xprompts/skills/sase_project.md 5ms (unchanged)
src/sase/xprompts/skills/sase_questions.md 6ms (unchanged)
src/sase/xprompts/skills/sase_repo.md 11ms (unchanged)
src/sase/xprompts/skills/sase_run.md 21ms (unchanged)
src/sase/xprompts/skills/sase_sudo.md 7ms (unchanged)
src/sase/xprompts/skills/sase_var.md 8ms (unchanged)
src/sase/xprompts/skills/SKILL.frame.template.md 1ms (unchanged)
src/sase/xprompts/split_file.md 2ms (unchanged)
src/sase/xprompts/summarize.md 2ms (unchanged)
src/sase/xprompts/t.md 2ms (unchanged)
src/sase/xprompts/tribe.md 2ms (unchanged)
tests/ace/tui/artifacts_contract/fixtures/notes/hello__a.md 2ms (unchanged)
tests/ace/tui/artifacts_contract/fixtures/notes/hello.md 1ms (unchanged)
tests/ace/tui/repro/README.md 5ms (unchanged)
tests/fixtures/agy/README.md 3ms (unchanged)
tests/fixtures/codex_stream/README.md 3ms (unchanged)
tests/fixtures/qwen_stream/README.md 2ms (unchanged)
tests/perf/README.md 26ms (unchanged)
tests/plan_chain_golden/README.md 5ms (unchanged)
tools/AGENTS.md 10ms (unchanged)
tools/CLAUDE.md 9ms (unchanged)
tools/GEMINI.md 13ms (unchanged)
tools/OPENCODE.md 10ms (unchanged)
tools/QWEN.md 9ms (unchanged)

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
[core-floor-probe] stale_actionable: sase-core-rs==0.34.48 is missing 21 capability(s) that exist in a published sase-core release.
[core-floor-probe] agent_hold_deadlock_reaches: first appears in sase-core 0a7301c (feat(hold): walk every wait branch for hold deadlock reachability); release v0.34.62 contains it.
[core-floor-probe] agent_hold_summarize_capture: first appears in sase-core 6fe31cb (feat(hold): persist capture summaries and return prune evidence); release v0.34.61 contains it.
[core-floor-probe] bead_set_link_projections: first appears in sase-core d32591f (feat(bead): add atomic bulk link-projection mutation); release v0.34.53 contains it.
[core-floor-probe] select_remaining_commit_obligations: first appears in sase-core 8d5341a (feat(finalizer): select remaining declared repos after repair); release v0.34.53 contains it.
[core-floor-probe] sudo_authorize_settlement: first appears in sase-core 9e1ab3f (feat(sudo): add completion authorization core contracts); release v0.34.54 contains it.
[core-floor-probe] sudo_classify_attempt_liveness: first appears in sase-core 9e1ab3f (feat(sudo): add completion authorization core contracts); release v0.34.54 contains it.
[core-floor-probe] sudo_validate_handshake: first appears in sase-core b70e64d (feat(sudo): add detached runner execution); release v0.34.52 contains it.
[core-floor-probe] tool_run_append_event: first appears in sase-core 44b82c3 (feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind); release v0.34.63 contains it.
[core-floor-probe] tool_run_begin: first appears in sase-core 44b82c3 (feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind); release v0.34.63 contains it.
[core-floor-probe] tool_run_canonicalize_fingerprint: first appears in sase-core 44b82c3 (feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind); release v0.34.63 contains it.
[core-floor-probe] tool_run_finish: first appears in sase-core 44b82c3 (feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind); release v0.34.63 contains it.
[core-floor-probe] tool_run_list: first appears in sase-core 44b82c3 (feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind); release v0.34.63 contains it.
[core-floor-probe] tool_run_normalize_definition: first appears in sase-core 44b82c3 (feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind); release v0.34.63 contains it.
[core-floor-probe] tool_run_reconcile: first appears in sase-core 44b82c3 (feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind); release v0.34.63 contains it.
[core-floor-probe] tool_run_retention_apply: first appears in sase-core 44b82c3 (feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind); release v0.34.63 contains it.
[core-floor-probe] tool_run_retention_preview: first appears in sase-core 44b82c3 (feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind); release v0.34.63 contains it.
[core-floor-probe] tool_run_show: first appears in sase-core 44b82c3 (feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind); release v0.34.63 contains it.
[core-floor-probe] tool_run_store_stats: first appears in sase-core 44b82c3 (feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind); release v0.34.63 contains it.
[core-floor-probe] tool_run_summary: first appears in sase-core 44b82c3 (feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind); release v0.34.63 contains it.
[core-floor-probe] tool_run_unknown_evidence: first appears in sase-core 44b82c3 (feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind); release v0.34.63 contains it.
[core-floor-probe] tool_run_wire_schema_version: first appears in sase-core 44b82c3 (feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind); release v0.34.63 contains it.
{"cache_hit": true, "capabilities": [{"commit": "0a7301c", "name": "agent_hold_deadlock_reaches", "release": "v0.34.62", "subject": "feat(hold): walk every wait branch for hold deadlock reachability"}, {"commit": "6fe31cb", "name": "agent_hold_summarize_capture", "release": "v0.34.61", "subject": "feat(hold): persist capture summaries and return prune evidence"}, {"commit": "d32591f", "name": "bead_set_link_projections", "release": "v0.34.53", "subject": "feat(bead): add atomic bulk link-projection mutation"}, {"commit": "8d5341a", "name": "select_remaining_commit_obligations", "release": "v0.34.53", "subject": "feat(finalizer): select remaining declared repos after repair"}, {"commit": "9e1ab3f", "name": "sudo_authorize_settlement", "release": "v0.34.54", "subject": "feat(sudo): add completion authorization core contracts"}, {"commit": "9e1ab3f", "name": "sudo_classify_attempt_liveness", "release": "v0.34.54", "subject": "feat(sudo): add completion authorization core contracts"}, {"commit": "b70e64d", "name": "sudo_validate_handshake", "release": "v0.34.52", "subject": "feat(sudo): add detached runner execution"}, {"commit": "44b82c3", "name": "tool_run_append_event", "release": "v0.34.63", "subject": "feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind"}, {"commit": "44b82c3", "name": "tool_run_begin", "release": "v0.34.63", "subject": "feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind"}, {"commit": "44b82c3", "name": "tool_run_canonicalize_fingerprint", "release": "v0.34.63", "subject": "feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind"}, {"commit": "44b82c3", "name": "tool_run_finish", "release": "v0.34.63", "subject": "feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind"}, {"commit": "44b82c3", "name": "tool_run_list", "release": "v0.34.63", "subject": "feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind"}, {"commit": "44b82c3", "name": "tool_run_normalize_definition", "release": "v0.34.63", "subject": "feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind"}, {"commit": "44b82c3", "name": "tool_run_reconcile", "release": "v0.34.63", "subject": "feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind"}, {"commit": "44b82c3", "name": "tool_run_retention_apply", "release": "v0.34.63", "subject": "feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind"}, {"commit": "44b82c3", "name": "tool_run_retention_preview", "release": "v0.34.63", "subject": "feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind"}, {"commit": "44b82c3", "name": "tool_run_show", "release": "v0.34.63", "subject": "feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind"}, {"commit": "44b82c3", "name": "tool_run_store_stats", "release": "v0.34.63", "subject": "feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind"}, {"commit": "44b82c3", "name": "tool_run_summary", "release": "v0.34.63", "subject": "feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind"}, {"commit": "44b82c3", "name": "tool_run_unknown_evidence", "release": "v0.34.63", "subject": "feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind"}, {"commit": "44b82c3", "name": "tool_run_wire_schema_version", "release": "v0.34.63", "subject": "feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind"}], "declared_floor": "0.34.48", "exit_code": 3, "message": "sase-core-rs==0.34.48 is missing 21 capability(s) that exist in a published sase-core release.", "status": "stale_actionable"}
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
created: 6/6 workers
6 workers [43383 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
.............................s.......................................... [  0%]
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
...............................s........................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................s............... [  5%]
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
...........F............................................................ [  7%]
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
...........s.....................................s..s................... [ 13%]
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
....s................................................................... [ 16%]
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
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 30%]
........................................................................ [ 30%]
...................................................................s.... [ 30%]
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
........................................................................ [ 48%]
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
.......................s................................................ [ 62%]
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
........................................................s.s...s...s..... [ 75%]
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
........................................................................ [ 88%]
........................................................................ [ 89%]
........................................................................ [ 89%]
.................................................F...................... [ 89%]
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
..............................................F......................... [ 95%]
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
.......................................                                  [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=================================== FAILURES ===================================
___________ test_x_does_not_toggle_the_host_on_nested_scheduler_rows ___________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

    def test_x_does_not_toggle_the_host_on_nested_scheduler_rows() -> None:
        host = _Host()
        host._axe_service_selection = None
        host._toggle_or_kill_axe_view()
>       assert host.calls == []
E       AssertionError: assert ['start-host'] == []
E         
E         Left contains one more item: 'start-host'
E         
E         Full diff:
E         - []
E         + [
E         +     'start-host',
E         + ]

tests/ace/tui/actions/test_service_host_keys.py:55: AssertionError
________________ test_tui_app_import_stays_under_startup_budget ________________
[gw1] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

    def test_tui_app_import_stays_under_startup_budget() -> None:
        """Importing the app should not pull known heavy deferred profile edges."""
    
        payload = _measure_tui_app_import()
        if payload["elapsed_seconds"] >= _MAX_ELAPSED_SECONDS:
            payload = _measure_tui_app_import()
>       assert payload["elapsed_seconds"] < _MAX_ELAPSED_SECONDS
E       assert 32.71686787693761 < 5.0

tests/ace/tui/test_app_import_budget.py:62: AssertionError
______ test_bootstrap_issue_enroll_hello_round_trip_through_real_gateway _______
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7ff571af3460>
tmp_path = PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-13/popen-gw0/test_bootstrap_issue_enroll_he0')
gateway = RealGateway(home=PosixPath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-13/popen-gw0/test_bootstrap_issue_enroll_he0...ath('/var/tmp/sase-02a72d87/pytest-of-bryan/pytest-13/popen-gw0/test_bootstrap_issue_enroll_he0/gw/loopback-cert.pem'))

    def test_bootstrap_issue_enroll_hello_round_trip_through_real_gateway(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
        gateway: RealGateway,
    ) -> None:
        redirect_sase_home(monkeypatch, gateway.home)
        issued = MachineService().issue_bootstrap()
        bundle_text = json.dumps(issued.bundle, sort_keys=True)
        bootstrap_secret = str(issued.bundle["bootstrap_secret"])
        assert bootstrap_secret not in repr(issued)
    
        client, config_dir = _client_service(monkeypatch, tmp_path, "client", gateway)
        result = client.add_machine(
            alias="apollo",
            endpoint=gateway.https_endpoint,
            provider_ref="builtin@https",
            bundle_text=bundle_text,
        )
    
        assert result.quarantined is False
        assert result.installation_id == issued.pinned_installation_id
    
        credential = client.credential_store.get(result.credential_ref)
        assert credential is not None
        assert credential.token
    
        config_text = (config_dir / "sase.yml").read_text(encoding="utf-8")
        assert credential.token not in config_text
        assert bootstrap_secret not in config_text
    
        (status,) = client.status(("apollo",))
>       assert status.state == "ok"
E       AssertionError: assert 'error' == 'ok'
E         
E         - ok
E         + error

tests/dispatch/test_machine_bootstrap_real_gateway.py:92: AssertionError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=3914984) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

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

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=3914981) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

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

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py: 18 warnings
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=3914975) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
- sase global leak detector: 12 poisoning change(s) across 12 test(s); 63179 warming mutation(s) filtered; 616 cooling mutation(s) filtered; 2796 invalidation(s) filtered; report=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/.pytest_cache/sase-global-leaks.json -
---------------- sase global leak detector blocking gate failed ----------------
============================= slowest 20 durations =============================
85.41s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
84.60s call     tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess
65.26s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
64.55s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
63.91s call     tests/ace/tui/test_app_title.py::test_on_mount_keeps_initial_title_when_resolver_returns_none
63.69s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
59.56s call     tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget
43.03s call     tests/ace/tui/test_patch_filter_bar.py::test_patch_filter_submit_commits_history_and_last_query
38.54s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
37.37s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
34.60s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
28.18s call     tests/attachments/test_markdown_pdf_properties.py::test_render_markdown_pdf_properties_smoke_when_tools_available[title: Tale PDF\ntier: tale\ngoal: Verify the card]
26.42s call     tests/test_config_reader_probe.py::test_cross_test_config_reader_is_reported_as_poisoning
26.32s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
21.76s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
19.49s teardown tests/ace/tui/test_artifacts_agents_loading.py::test_agent_first_page_paints_before_full_extension
19.28s call     tests/test_command_palette_e2e.py::test_colon_opens_command_palette_from_agents_tab
17.23s call     tests/ace/tui/test_artifacts_beads_filtering.py::test_hide_closed_default_is_visible_and_clearable
17.01s call     tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_confirm_executes_and_restarts
16.82s call     tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py::test_updates_pane_sase_update_dev_confirm_closes_admin_center
=========================== short test summary info ============================
FAILED tests/ace/tui/actions/test_service_host_keys.py::test_x_does_not_toggle_the_host_on_nested_scheduler_rows - AssertionError: assert ['start-host'] == []
  
  Left contains one more item: 'start-host'
  
  Full diff:
  - []
  + [
  +     'start-host',
  + ]
FAILED tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget - assert 32.71686787693761 < 5.0
FAILED tests/dispatch/test_machine_bootstrap_real_gateway.py::test_bootstrap_issue_enroll_hello_round_trip_through_real_gateway - AssertionError: assert 'error' == 'ok'
  
  - ok
  + error
==== 3 failed, 43366 passed, 15 skipped, 85 warnings in 4263.80s (1:11:03) =====
error: recipe `test-cost` failed on line 453 with exit code 1
error: recipe `check-full` failed on line 737 with exit code 1

