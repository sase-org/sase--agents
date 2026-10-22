# Chat History - ace-run (research.2v.gem)

- **TIMESTAMP:** 2026-09-28 05:59:35 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2v.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260928_052837.md`

## Prompt

%id(gem, clan=research.2v)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.2v.cdx`, `research.2v.cld`, `research.2v.grk`, `research.2v.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

It's been a while
since sase released a version to PyPI. This is because master is always red. I need to
fix these failing CI jobs and release the next version to PyPI.

Can you do some research with the goal of helping me figure out what needs to be done?
End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Report: Fixing Master CI and Releasing the Next Version to PyPI

**Author**: `research.2v.gem`  
**Report File**: [`fix_master_ci_and_pypi_release__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/sase/repos/research/202609/fix_master_ci_and_pypi_release__gem.md)  
**Registered Artifact Ref**: `file:explicit:e04b7b45d90259bd54d30287` (`research:202609/fix_master_ci_and_pypi_release__gem.md`)  

---

## 1. Executive Summary

The `sase` project has not released a new version to PyPI in approximately one month (`0.17.1` is current; pending release is `0.18.0`). Over 840 commits have landed on `master` since the last green CI build on September 18, 2026 (`f90c6b549f6e`).

The release outage is caused by **two interrelated blockers**:
1. **The PyPI Core-Floor Smoke Blocker**: `sase` on `master` already requires 10+ new Rust core bindings (`tool_run_briefs`, `managed_tmp_roots`, `canonicalize_agent_tab_name`, `goal_card_view`, etc.). When release candidates are tested (`release-core-floor-smoke` in [`.github/workflows/ci.yml`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/.github/workflows/ci.yml) and `install-smoke-core-floor` in [`.github/workflows/publish.yml`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/.github/workflows/publish.yml)), CI installs the latest published `sase-core-rs` wheel from PyPI (`0.35.1`), which lacks these bindings and fails with an exit code 1. Pending PR `#315` in `sase-org/sase-core` (`chore: release v0.36.0`) is waiting to publish `0.36.0` to PyPI.
2. **Twelve Master Gate CI Regressions**: Even when using a locally built core wheel, `Master Gate` fails across `lint` and test shards 2, 3, 4, 5, 6, and 7 due to accumulated regressions, line count limits (`_lint-toobig`), uncaptioned CLI completion value slots, missing schema properties, and stale assertions.

---

## 2. Root Cause Analysis: PyPI Release Blockers

### Why Release PR #299 Is Blocked
The pending release PR ([`#299 chore(master): release 0.18.0`](https://github.com/sase-org/sase/pull/299)) managed by `release-please` has been open for 28 days with status `mergeStateStatus: UNSTABLE`. The failing check is:
```
CI/release-core-floor-smoke (pull_request)
sase_core_rs 0.35.1 is missing 10 of 725 required binding(s):
  build_agent_tab_catalog, canonicalize_agent_tab_name,
  launch_scratch_liveness_wire_schema_version, managed_tmp_roots_list,
  managed_tmp_roots_register, managed_tmp_roots_wire_schema_version,
  observe_launch_scratch_liveness, tool_run_briefs, tool_run_live_glance,
  tool_run_node_summaries
```
This check ensures that any wheel published to PyPI will function when users install it alongside the published `sase-core-rs` floor. Because `sase-core-rs 0.36.0` has not yet been published to PyPI, any release attempt fails closed.

---

## 3. Root Cause Analysis: Master Gate Failures

Every failure on `master` has been isolated and verified:

1. **Unratcheted [`sase-core-revision.txt`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/sase-core-revision.txt)**:
   - Commit `17d2beb767` (`sase-1bu.6`) added `goal_card_view`, `goal_card_markdown`, and `goal_citation_line` to [`tools/validate_sase_core_rs`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/tools/validate_sase_core_rs) and added [`tests/goals/test_goal_artifact_kind.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/tests/goals/test_goal_artifact_kind.py).
   - In `sase-core`, commit `33b0250` added those bindings to `sase_core_py`. However, `sase-core-revision.txt` was not bumped from `cbe70f66` to `33b0250f`.
   - *Result*: `lint` fails `tools/check_sase_core_rs_bindings`, and tests fail `AttributeError: missing binding 'goal_card_view'`.

2. **File Length Violations in [`_lint-toobig`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/Justfile)**:
   - [`src/sase/core/tool_run.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/src/sase/core/tool_run.py) has 1,154 lines (limit 1,000).
   - [`src/sase/tool/executor.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/src/sase/tool/executor.py) has 1,175 lines (limit 1,000).
   - *Result*: `just _lint-toobig` fails.

3. **Schema Missing `receipt` Property in [`src/sase/config/sase.schema.json`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/src/sase/config/sase.schema.json)**:
   - Commit `3065117500` added `receipt: ...` to `tools.check` in [`sase/sase.yml`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/sase/sase.yml) but did not add `receipt` to `"toolDefinition"` in `sase.schema.json`.
   - *Result*: [`tests/test_config_schema_tools.py::test_project_sase_yml_matches_public_schema`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/tests/test_config_schema_tools.py) fails with `Additional properties are not allowed ('receipt' was unexpected)`.

4. **Uncaptioned Completion Value Slots for `tool receipt(s)`**:
   - Subcommands `tool receipt` and `tool receipts` were added to the CLI parser without registering value kinds or hints in [`src/sase/completion/kinds.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/src/sase/completion/kinds.py).
   - *Result*: [`tests/completion/test_kind_coverage.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/tests/completion/test_kind_coverage.py) and [`tests/completion/test_snapshot.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/tests/completion/test_snapshot.py) fail.

5. **Agent Completion Candidate Regression from `%tab`**:
   - Commit `372ecc97c3` injected a `('tab', 'main')` candidate into [`build_agent_completion_candidates`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/src/sase/ace/tui/_agent_completion_candidates.py).
   - *Result*: 9 unit tests in [`tests/ace/tui/test_agent_completion.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/tests/ace/tui/test_agent_completion.py) fail because they expect the candidate list without tab candidates.

6. **Missing `agent_meta` on Mock Context**:
   - [`src/sase/axe/run_agent_exec.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/src/sase/axe/run_agent_exec.py) accesses `ctx.agent_meta`, but mock setups in [`tests/test_axe_run_agent_exec_repeat_env.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/tests/test_axe_run_agent_exec_repeat_env.py) use `MagicMock(spec=AgentExecContext)` without setting `ctx.agent_meta = {}`.
   - *Result*: 6 tests fail with `AttributeError: Mock object has no attribute 'agent_meta'`.

7. **Stale Wording Assertion in Getting Started Docs Test**:
   - Commit `90d6138504` rephrased [`docs/getting_started.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/docs/getting_started.md).
   - *Result*: [`tests/test_docs_getting_started_providers.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/tests/test_docs_getting_started_providers.py) fails asserting the old text.

8. **Stale Prompt Trash Limit Assertion**:
   - Commit `1ec4569d87` increased the trash limit from 20 to 100.
   - *Result*: [`tests/ace/tui/actions/test_prompts_overlay_entry_points.py:117`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/tests/ace/tui/actions/test_prompts_overlay_entry_points.py) asserts `modal._trash_limit == 20` and fails (`100 == 20`).

9. **Directive Completion Prefix Collision**:
   - Removal tests for `%tale` and `%tribe` tested prefixes `%ta` and `%t` expecting empty results, which now collide with the new `%tab` directive.
   - *Result*: [`tests/ace/tui/widgets/test_directive_completion_candidates.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/tests/ace/tui/widgets/test_directive_completion_candidates.py) fails.

10. **Unreviewed Marker Path Passing Sites**:
    - Sites in [`src/sase/axe/run_agent_directive_metadata.py:session_root_tab`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/src/sase/axe/run_agent_directive_metadata.py) and [`src/sase/finalizers/cli.py:_target_for_dir`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/src/sase/finalizers/cli.py) were added without registering them in [`tests/test_agent_artifact_marker_path_passing_audit.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/tests/test_agent_artifact_marker_path_passing_audit.py).
    - *Result*: Architectural audit test fails.

11. **System Clock Display Guard Violations**:
    - Raw calls to `datetime.fromtimestamp(...)` and `datetime.now()` were added in `src/sase/ace/tui/tool_runs/blocks.py`, `update_gear.py`, `update_panel_state.py`, and `src/sase/tool/view_vocabulary.py`.
    - *Result*: [`tests/test_timezone_display_guard.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/tests/test_timezone_display_guard.py) fails.

12. **Textual Pilot Timing Flakes**:
    - In [`tests/ace/tui/widgets/test_agent_header_panel.py:694`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/tests/ace/tui/widgets/test_agent_header_panel.py), `main_view.pin_to_bottom()` triggers an asynchronous layout adjust. Without an immediate `await pilot.pause()`, reading `deck_y` samples before layout settles, causing `assert 2.0 == 0.0`.
    - Terminal resize in [`tests/ace/tui/command_line/test_chrome_layout.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/tests/ace/tui/command_line/test_chrome_layout.py) occasionally asserts before width updates under high CI load.

---

## 4. Recommended Solution: Step-by-Step Action Plan

### Phase 1: Release `sase-core-rs 0.36.0` to PyPI
1. In repository `sase-org/sase-core`:
   - Merge PR #315 (`chore: release v0.36.0`).
   - Allow `release-plz` to run, tag `v0.36.0`, and publish `sase-core-rs==0.36.0` wheels to PyPI.
   - Confirm publication with `pip index versions sase-core-rs`.

### Phase 2: Ratchet Core Pin and Window in `sase`
1. Update [`sase-core-revision.txt`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/sase-core-revision.txt) to commit `33b0250f91b81ebe9913796574e5faf787f741cf`.
2. Run `python tools/ratchet_core_window --allow-transitive-lock-refresh` to advance [`pyproject.toml`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_47/pyproject.toml) to `sase-core-rs>=0.36.0,<0.37.0` and update `uv.lock`.

### Phase 3: Apply Code Fixes in `sase`
1. **Split files exceeding 1,000 lines**:
   - Extract ledger query/projections from `src/sase/core/tool_run.py` into a submodule (e.g. `src/sase/core/tool_run_projections.py`).
   - Extract settlement/reporting routines from `src/sase/tool/executor.py` into focused submodules under 500 lines.
2. **Schema and completion sync**:
   - Add `"receipt"` definition to `"toolDefinition"` in `src/sase/config/sase.schema.json`.
   - Register `tool_receipt_tool` and `tool_receipts_days` in `src/sase/completion/kinds.py`, then run `just sync-completion-spec`.
3. **Timezone and audit compliance**:
   - Route timestamp formatting in `blocks.py`, `update_gear.py`, `update_panel_state.py`, and `view_vocabulary.py` through `sase.core.time`.
   - Add `session_root_tab` and `_target_for_dir` to `_REVIEWED_PATH_PASSING_CONTEXTS` in `tests/test_agent_artifact_marker_path_passing_audit.py`.
4. **Fix test assertions and mocks**:
   - In `tests/ace/tui/actions/test_prompts_overlay_entry_points.py`, update trash limit assertion to `100`.
   - In `tests/test_docs_getting_started_providers.py`, update doc assertion to match `docs/getting_started.md`.
   - In `tests/test_axe_run_agent_exec_repeat_env.py`, set `ctx.agent_meta = {}`.
   - In `tests/ace/tui/widgets/test_directive_completion_candidates.py`, test `%tale` and `%tribe` explicitly.
   - In `tests/ace/tui/test_agent_completion.py`, update candidate expectations to include `'main'` tab.
   - In `tests/ace/tui/widgets/test_agent_header_panel.py:694`, add `await pilot.pause()` after `main_view.pin_to_bottom()`.

### Phase 4: Land and Verify Green Master Gate
1. Execute `just check` locally (both lint and test suites).
2. Land changes on `master` and verify all 8 test shards and lint in `Master Gate` turn green (`✓`).

### Phase 5: Reconcile Release PR and Publish to PyPI
1. Trigger `publish.yml` via `workflow_dispatch` (or wait for the 3-hour cron). Release Please will update PR #299 with all commits up to the new green `master`.
2. Confirm that `release-core-floor-smoke` passes on PR #299 against `sase-core-rs==0.36.0`.
3. Merge PR #299 into `master`.
4. `publish.yml` triggers on the merge, builds wheels, validates smoke tests, and publishes `sase 0.18.0` to PyPI.
