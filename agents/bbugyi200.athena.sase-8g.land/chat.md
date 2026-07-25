# Chat History - ace-run

- **TIMESTAMP:** 2026-07-21 07:43:25 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** sase-8g.land

## Prompt

%id(land, clan=sase-8g)
#gh:gh_sase-org__sase
%model:@big_epic_lander
%auto
%w:sase-8g.1,sase-8g.2,sase-8g.3,sase-8g.4,sase-8g.5,sase-8g.6,sase-8g.7,sase-8g.8,sase-8g.9,sase-8g.10,sase-8g.11
%w(bead=sase-8g.1)
%w(bead=sase-8g.2)
%w(bead=sase-8g.3)
%w(bead=sase-8g.4)
%w(bead=sase-8g.5)
%w(bead=sase-8g.6)
%w(bead=sase-8g.7)
%w(bead=sase-8g.8)
%w(bead=sase-8g.9)
%w(bead=sase-8g.10)
%w(bead=sase-8g.11)
You are the land agent for epic bead sase-8g: verify the epic is truly complete, integrate it with changes
that landed since it started, then close it out.

1. Verify. Run `sase bead show sase-8g` (children, linked plan file), then `sase bead show` on each child
   bead. Confirm every bead note was addressed, and read the actual source code and the epic's commits (bead IDs
   appear in commit messages) to confirm the work previous agents reported complete really is.

2. Integrate. Changes committed since this epic started could not integrate with this epic's feature while it was
   incomplete. Find them (e.g. `git log` since the first commit mentioning sase-8g, excluding the epic's own
   commits; in a PR workflow also review commits on the base branch) and update anything that should now use what
   this epic added or that duplicates or conflicts with it. This integration is part of the epic's work.

3. Land. Close the epic with `sase bead close sase-8g`. AFTER closing, run `just symvision` if available
   (epic-symbol whitelist entries for sase-8g expire at close) and remove the stale entries and unused code
   it reports. Finally, set `status: done` in the frontmatter of the epic's plan file (the PLAN path shown by
   `sase bead show`).

If steps 1-2 uncover remaining work, use your /sase_plan skill to plan it and complete the skill's tier-aware
validate/revalidate/propose loop. Make step 3 the plan's final phase (close, run symvision, mark the plan file done)
so the agent that executes the plan finishes the landing. Otherwise do step 3 now.

## Response

I'll start by verifying the epic bead sase-8g and its children.

sase-8g.4 (47f6df24b) predates that range — let me anchor on it and see the full window.

Now let me read both commit diffs in full.

I'll start by locating and reading the plan file, and pulling the two commits.

The plan file exists. Now let me read it and pull both full diffs.

Now let me read the full diffs of both commits.

Phase 2's diff is captured. Now the full diff of phase 8's commit.

I have the plan. Now let me read the full commit diff.

Now let me read both commit diffs in full.

The docs commits edited neighboring paragraphs, not the help-binding entries — but I'll confirm they still exist at HEAD. Let me verify all current sources.

Now let me read both commit diffs in full.

Now the tests from the commit, then the current HEAD state.

All five doc entries survive at HEAD. Now let me read the current sources and the moved binding test, and check the COMMITS branch handling for phase 1 item 3.

Now the split helper modules and _store_link.py at HEAD.

The fork logic survived the refactor. Now let me read the current state of the phase-2 files and validation.

No new file-write sinks in the non-epic feature commits — nothing needs the epic's rotation/guard helpers. Let me check the symvision setup while waiting.

The self-heal logic survived the git-helpers split intact. Now check the snapshot module and the tests at HEAD.

No sase-8g symbol-whitelist pragmas exist in source. Let me check how the plan file path is tracked (primary repo vs plans sidecar).

Setup verification is done. Here's where things stand while the verification agents work:

- **Epic state**: all 11 children closed, each with a landed commit on master (the bead notes record pre-rebase hashes; I matched every phase to its rebased commit, sase-8g.4 first at 07-20 16:48 through sase-8g.11 at 17:41).
- **Integration scan (my own pass)**: ~18 non-epic commits landed since the epic started. The substantive ones (sase-8f.2/8f.3 bead-claiming, sase-8d plan-path fix, clan-declaration fix) introduce no new log sinks or writers that should adopt the epic's rotation/atomic-append/pytest-guard helpers. The four post-epic refactors split the exact modules the epic modified (axe ensure, run-agent directives, SDD recovery/transaction) — I've tasked the phase verifiers with confirming the epic's logic survived those splits.
- **Landing prep**: `just install` completed, `just symvision` exists, and no `sase-8g` whitelist pragmas remain in source. The plan file lives in the plans sidecar checkout; I'll open it through the repo skill before editing its frontmatter.

Seven verification agents are now reviewing each phase's commit against the plan's fix/test requirements and current HEAD. I'll consolidate their findings when they report back.

The refactored `_repository_integration.py` at HEAD preserves the commit's logic. Now let me check the sync/push wiring, the launch-time manifest validation path, and search for the rollback-conflict test.

All tests exist at HEAD. Let me run the targeted tests to confirm they pass in this workspace, and check how `_marker_priority` derives priority.

All phase-4 code intact at HEAD, and the AxeConfigError propagation path (`_process_status.py:45,101` → caught at `_data.py:194,214`) checks out. Now the tests at HEAD.

VERDICT: complete

Phase sase-8g.5 was genuinely implemented as specified in `sase/repos/plans/202607/audit_24h_fixes.md` (section "Self-heal wedged SDD sidecar clones", lines 242-264), and the logic survived both post-epic refactors intact. All 29 tests in the two affected test files pass at HEAD (ran `.venv/bin/pytest tests/sdd_store/test_repository_transaction.py tests/sdd_store/test_sidecar_clone.py`: 29 passed in 4.36s).

Per plan-item verification (all paths under /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12):

Fix item 1 — self-heal on dirty machine-managed pull failure, snapshot-then-reset, bounded, one axe digest: PASS
- Trigger: `_pull_sdd_clone` now calls `integrate_machine_managed_sdd_repository` (src/sase/sdd/_store_link.py:289-293), which falls through to `recover_machine_managed_sdd_repository` on any non-success/non-REMOTE_UNAVAILABLE outcome (src/sase/sdd/_repository_transaction.py:115-133).
- Snapshot before reset: timestamped ref `refs/sase/recovery/<UTC-ts>-<branch>-<hash>` created and verified against pre-reset branch head (src/sase/sdd/_repository_recovery.py:148-179; ref format src/sase/sdd/_repository_recovery_git.py:101-106), then dirty tracked/staged/untracked state stashed with `--include-untracked` and the recovery ref repointed at the verified stash SHA (src/sase/sdd/_repository_recovery_snapshot.py:78-123). Plan allowed "recovery branch or a stash entry" — implemented as a timestamped ref plus stash entry, with content verification (`_verify_stash_snapshot`, snapshot module lines 163-189).
- Hard-reset + re-pull: `reset --hard <upstream>` with post-reset verification, then a retry integration inside the same lock; success returns status RECOVERED with `recovery_ref` (src/sase/sdd/_repository_recovery.py:266-325).
- Bounded once per window: durable JSON attempt-marker in the clone's .git dir; a recent marker short-circuits to RECOVERY_COOLDOWN without touching the clone (src/sase/sdd/_repository_recovery.py:110-131); default cooldown max(300s, bead-refresh TTL) (src/sase/sdd/_repository_recovery_git.py:206-213).
- One axe error-digest entry on repeated failure: RECOVERY_FAILED/UNRECOVERABLE outcomes gate `_append_recovery_error` (writes via `sase.axe.state.append_error`) behind `admit_recovery_notice(report=True)` with a 3600s durable cooldown (src/sase/sdd/_store_link.py:316-325, 340-368; src/sase/sdd/_repository_recovery_markers.py:22-24, 40-79).

Fix item 2 — rate-limit per-tick failure logging regardless: PASS
- The "Failed to pull workspace SDD clone" warning is admitted only through `admit_recovery_notice` (900s = 15 min cooldown per clone + failure signature; signature = sha256 of clone path + status + error detail, so identical messages are suppressed while a new failure logs immediately) (src/sase/sdd/_store_link.py:308-315; src/sase/sdd/_repository_recovery_markers.py:23, 27-37, 57-58). RECOVERY_COOLDOWN returns silently with no log at all (src/sase/sdd/_store_link.py:305-306).

Fix item 3 — clear leftover rebase-in-progress state: PASS
- When operation markers exist, recovery aborts the stale rebase and fails closed unless `verify_rebase_cleared` proves markers and unmerged entries are gone (src/sase/sdd/_repository_recovery.py:181-207; src/sase/sdd/_repository_recovery_git.py:133-149). The original branch is proven from `rebase-merge`/`rebase-apply` `head-name` (src/sase/sdd/_repository_recovery_git.py:45-56). Non-rebase operations (e.g. merge) are refused (lines 32-37).

Plan-required tests: PASS — all exist at HEAD and pass
- Dirty clone + diverged remote → snapshot, reset, successful re-integration, snapshot ref contains dirty tracked/staged/untracked content: tests/sdd_store/test_repository_transaction.py:231-272 (`test_machine_managed_recovery_snapshots_dirty_index_and_untracked_files`). Note: "second pull succeeds" is realized as the retry integration inside the recovery transaction (asserted via RECOVERED + HEAD == remote head + clean status), not a literal second `_pull_sdd_clone` call — semantically equivalent.
- Repeated failure not re-attempted within window (and reopens after): tests/sdd_store/test_repository_transaction.py:360-406 (asserts exactly 1 attempt, second call RECOVERY_COOLDOWN, re-attempt after window).
- Rebase-merge/rebase-apply cleanup: tests/sdd_store/test_repository_transaction.py:191-229, parametrized over both backends, asserts both marker dirs gone.
- Rate-limited warning + single axe digest entry, durable, reopening after 3601s: tests/sdd_store/test_sidecar_clone.py:82-153.
- Bonus safety coverage: generic (non-machine-managed) integration still preserves dirty state with no recovery refs (test_repository_transaction.py:274-298); failed snapshot never resets the branch (lines 301-357); unrelated merge state refused untouched (lines 408-430).

Post-epic refactor integration: no issues
- 117a19cd0 split `_repository_recovery.py` into `_repository_recovery_git.py` / `_repository_recovery_markers.py` / `_repository_recovery_snapshot.py`; the orchestration flow in `_repository_recovery.py:46-325` and all helper bodies are logic-identical to the phase commit (renames only, e.g. `_snapshot_managed_changes` → `snapshot_managed_changes`).
- 5c93569d8 turned `_repository_transaction.py` into a facade over `_repository_types.py` / `_repository_health.py` / `_repository_integration.py`; the RECOVERED/RECOVERY_COOLDOWN/RECOVERY_FAILED statuses, `recovery_ref` field, and RECOVERED-counts-as-succeeded semantics live in src/sase/sdd/_repository_types.py:21-23, 66, 69-73, and `integrate_machine_managed_sdd_repository` is preserved at src/sase/sdd/_repository_transaction.py:83-141.
- `git diff e7c768070..HEAD -- tests/sdd_store/test_repository_transaction.py tests/sdd_store/test_sidecar_clone.py src/sase/sdd/_store_link.py` is empty — the caller wiring and both test files are byte-identical to the phase commit.

One behavior change worth noting (consistent with the plan's anti-spam intent, not a gap): at the phase commit, non-strict UNRECOVERABLE outcomes in `_pull_sdd_clone` stopped raising `SddRepositoryHealthError` and now return False after the rate-limited warning/report (src/sase/sdd/_store_link.py:327-332) — this is what stops one wedged clone from throwing per-tick in the lumberjacks.

# Verification Report: Epic sase-8g, Phases .1 and .9

## Phase sase-8g.1 — "Converge hooks suffix-transform writes" (commit 84da4721c)

**VERDICT: complete.**

Plan-item results (plan: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/plans/202607/audit_24h_fixes.md:129-144`):

1. **Fresh-read transform helper, both transforms routed through it — PASS.** `transform_changespec_hooks_field` (`src/sase/ace/hooks/persistence.py:116`) parses the ChangeSpec from disk after acquiring `changespec_lock` (persistence.py:138) and applies a pure `fn(list[HookEntry]) -> list[HookEntry]`, exactly the shape the plan proposed. `update_hook_status_line_suffix_type` (persistence.py:253) was rewritten as a pure transform routed through it, and `strip_terminal_status_markers` now builds its hook rewrite inside the locked fresh read (`src/sase/ace/scheduler/suffix_transforms.py:244-258`, helper `_transform_terminal_hook_suffixes` at :150). Update messages are computed from the fresh disk state inside the transform, not the stale snapshot.
2. **Idempotence / no-op suppression — PASS.** The helper skips the write and returns False when the transform is a no-op (persistence.py:150), and `write_hooks_unlocked` additionally returns False when serialized content is unchanged (persistence.py:55). `strip_terminal_status_markers` extends its `updates` list only on a True return (suffix_transforms.py:253-258), so a pathological state produces zero log messages per tick.
3. **COMMENTS/COMMITS branches — PASS.** COMMENTS got the same helper: `transform_changespec_comments_field` (`src/sase/ace/comments/operations.py:192`, no-op guard at :220), used by the terminal cleanup (suffix_transforms.py:264-276) and by `clear_comment_suffix` (operations.py:382). COMMITS did not need conversion — the plan's item was conditional ("if they share the snapshot-write pattern"), and `update_commit_entry_suffix` (`src/sase/workflows/commit_utils/modifiers.py:212-215`) already re-reads file lines under `changespec_lock` and only rewrites a line that still carries a suffix on disk (regex at modifiers.py:247-250), so a stale snapshot can't restore a stripped suffix and repeat calls return False.

**Tests — PASS.** `tests/test_suffix_transform_persistence.py` (new in the commit, unchanged at HEAD) contains the exact interleave the plan demands: `test_terminal_hook_cleanup_does_not_restore_old_entry_marker` (:752) parses a stale ChangeSpec, applies a concurrent on-disk change, runs a fresh-read strip (`strip_old_entry_error_markers`, :786), then `strip_terminal_status_markers` with the stale object, and asserts the stripped line stays stripped (:796), the concurrent hook survives (:797-801), and a second run yields `[]` with no write (inode check, :803-805). Companion tests cover material-change-only writes (:699), targeted-update idempotence (:734), running_agent→killed_agent conversion (:808), and comment concurrent-change preservation with second-run idempotence (:827-867). `tests/test_acknowledge_terminal_status.py` was updated to the new transform API. All 16 tests pass at HEAD.

**HEAD integrity:** `git log 84da4721c..HEAD` on all phase-1 files is empty — HEAD state is exactly the commit state.

## Phase sase-8g.9 — "Close display and help-binding gaps" (commit e898a65ba)

**VERDICT: complete** (one minor test-coverage note).

Plan-item results (plan :351-368):

1. **Mobile subtitle humanization — PASS.** `subtitle()` at `src/sase/integrations/_mobile_agent_summary.py:228-231` maps through `project_display_name_for`; the machine-readable `agent["project"]` field keeps the canonical key. Test `test_list_mobile_agents_humanizes_display_subtitle_project` (`tests/test_mobile_agent_listing.py:42`) asserts both (raw key in `agent["project"]`, humanized label in `display.subtitle`, key absent from subtitle). Passes.
2. **XPrompt browser group headers — PASS.** All three cited sites humanized at HEAD: `src/sase/ace/tui/modals/xprompt_browser_helpers.py:96-97` (project_local_config), :123-125 (Project home), :143-145 (Project home, legacy); source labels/paths untouched.
3. **Statistics help modal close key — PASS.** The hard-coded `question_mark` close binding was removed from `BINDINGS`; the configured `keymaps.help` key is installed as a priority close binding via `BindingsMap` in `__init__` (`src/sase/ace/tui/modals/statistics_help_modal.py:73-84`) and the footer renders it through `key_display_name` (:91-95). Proven working end-to-end by the passing remapped-key test below.
4. **Docs enumerations — PASS.** All five additions present at HEAD: `docs/configuration.md:376` (sample YAML) and :486 (actions table row), `docs/telemetry.md:189` (key table row) and :221 (override YAML), `docs/ace.md:2192` (override example `help: "f9"`).

**Tests — PASS** with one note. The modal open/close-symmetry test with a remapped key (`help: "f5"`) survived the post-epic test-file split (937016404) and now lives at `tests/ace/tui/test_statistics_pane_bindings.py:74-93`, asserting open on f5, footer text `f5/q/Esc close`, and close on the same f5. Browser-header humanization is asserted at `tests/test_project_local_xprompts.py:214`. All pass at HEAD. Minor note: only the `project_local_config` branch of `classify_source` has a humanization assert; the two "Project home" branches (helpers.py:123, :143) are humanized in code but have no dedicated test (no test references "Project home"). The plan's test line is satisfied as written, so I flag this as a gap-adjacent observation, not a failure.

**Post-epic docs commits — no conflict.** `d369a98ce` and `717abb8ec` edited adjacent Statistics/telemetry paragraphs (scope chips, project-filter semantics, legend wording) but did not touch or contradict any of the five help-binding doc entries; both commits actually reinforce them (e.g. "`?` opens the complete glossary" wording retained in docs/configuration.md and docs/telemetry.md). The only phase-9 code path they touched is documentation; `statistics_help_modal.py`, `xprompt_browser_helpers.py`, and `_mobile_agent_summary.py` are byte-identical to the commit at HEAD.

**Test evidence:** 16/16 phase-1-related tests and 3/3 statistics-binding tests pass when run at HEAD with the workspace venv.

Phase 5 (SDD sidecar self-heal) verified complete — snapshot-then-reset recovery, cooldown bounding, rate-limited logging, and rebase-state cleanup all confirmed at HEAD, with the logic intact through both post-epic SDD refactors and all 29 related tests passing. Six phase verifications still running; I'll consolidate as they report.

Phases 1 and 9 verified complete as well — the fresh-read locked transform helper, idempotent no-op suppression, all display/doc gap fixes, and their required tests all confirmed at HEAD (docs commits after the epic didn't contradict them). Five verifications remain (phases 2+8, 3, 4+6, 7, 10+11).

VERDICT: complete — all three defects plus the docs note were implemented as specified, the fix survives all post-epic refactors at current HEAD, and all associated tests exist and pass (10 test cases run, 10 passed).

Per plan-item results (all paths absolute under `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12`):

(a) Run Now releases parked slot waiter — PASS. `src/sase/ace/tui/actions/agents/_wait_actions.py:126-128` routes `result.run_now and agent.slot_requested_at` into `_apply_live_runner_wait` (the plan's preferred option: rewrite the marker to the implicit global-cap threshold via `wait_runners=None`, `_wait_actions.py:283-297`), so no `ready.json`/`unwait` is written; the runner-consumed `waiting.json` marker is the release mechanism. The dead-path hazard (`_directive_persistence.py:273-275` FileExistsError on existing ready.json) is no longer reachable from this flow. The existing test `tests/ace/tui/test_agent_wait_resume.py:179` (`test_apply_wait_run_now_releases_parked_runner_slot`) was strengthened exactly as required: after the TUI apply it asserts no ready.json, then calls the real runner-side `run_agent_wait._try_claim_runner_slot` and asserts `claimed == "started"`, `parked is False`, and `waiting.json` removed — a genuine end-to-end release assertion. Passes at HEAD.

(b) Question-yield requeue preserves priority — PASS. `src/sase/axe/run_agent_exec_questions.py:169` now passes `wait_priority=normalize_wait_priority(base_meta.get("wait_priority"))` (using the plan-mandated single normalization helper from `src/sase/core/runner_slots/_admission.py:15`). `wait_priority` added to `AgentMetaWire` at `src/sase/core/agent_scan_wire_markers.py:158` (class at :95), with schema bump 17→18 (`agent_scan_wire_records.py:27`) and pinned-version test updated. Rust boundary respected correctly: the wire dataclass lives in this repo's Python; the Rust scan binding returns the raw agent_meta dict which `_agent_meta_from_dict` filters via `known_field_kwargs` (`src/sase/core/agent_scan_wire_conversion.py:175-186`), confirmed behaviorally — `tests/test_core_agent_scan_options.py:128` exercises the real Rust-backed `scan_agent_artifact_dirs` and passes (wait_priority=4 preserved, legacy meta → None). Parametrized normalization coverage (3→3, None→10, -1→10, "3"→10) in `tests/test_axe_run_agent_exec_plan_followup_questions.py:38`; TUI enrichment fallbacks in `_meta_enrichment_filesystem.py:323-326` and `_meta_enrichment_wire.py:211-215` with tests in `tests/test_enrich_agent_waiting.py:52`.

(c) Slot poll preserves foreign marker keys — PASS (took the "preserve" option, not the removal alternative). `src/sase/axe/run_agent_wait.py:322-331` now does `marker = dict(waiting_data or {})` then `marker.update({...seven keys...})` instead of rebuilding from a fixed set. `tests/test_run_agent_runner_slots.py:154` asserts across two consecutive polls that `waiting_for`, `wait_for_artifacts`, `wait_for_beads`, `wait_duration`, `wait_until`, `resolved_deps`, and an unknown `extension` key all survive rewrite while the owned keys refresh. Passes at HEAD.

(d) Docs note — PASS. Priority-then-FIFO-no-aging/starvation documented in both `docs/troubleshooting/runner-slots.md:12-14` and, next to the `%wait(priority=N)` documentation, `docs/xprompt.md:1073` and `:1261-1266`; question-continuation priority retention at `docs/xprompt.md:1276-1278`. Both notes survived the later docs commits (d369a98ce, 717abb8ec).

Risks-section e2e requirement — not triggered, coverage present anyway. This commit changed no admission ordering (only docstrings in `src/sase/core/runner_slots/_admission.py:81,115`), so extending `tests/fakey/test_runner_slots_e2e.py` was not required; priority-ordering e2e coverage already exists from 46c2f0622 (`test_fakey_priority_admission_differs_from_park_order`, line 343) and passes at HEAD.

Post-epic integration: cdb2af023 moved the wait_priority persistence site the plan cited at `run_agent_directives.py:444-445` into `src/sase/axe/run_agent_directive_metadata.py:150-151` (with `run_agent_directives.py:30,308` still threading the field) — the question-requeue read path at `run_agent_exec_questions.py:169` is unaffected. No integration breakage found. `_marker_priority` (`run_agent_wait.py:262-272`) gives a parked marker's edited priority precedence over the original directive, consistent with the pre-existing threshold-edit semantics.

Minor observation (not a gap): a freshly parked marker no longer seeds `waiting_for: []` (the merge starts from `waiting_data or {}`); all enrichment readers use `.get()` defaults and the full targeted suite plus fakey e2e pass, so no behavioral issue.

Phase 3 (runner-slot wait regressions) verified complete — Run Now genuinely releases parked waiters end-to-end, question-yield requeue preserves wait priority through the wire schema bump, foreign marker keys survive slot polls, and the priority-then-FIFO docs note landed. It also confirmed the post-epic directive-handling refactor didn't break the read path. Four verifications remain (phases 2+8, 4+6, 7, 10+11).

Verification complete. Both phases check out; full detail below.

---

## Phase sase-8g.4 "Degrade TUI axe status gracefully" — commit 47f6df24b

**VERDICT: COMPLETE**

| Plan item | Result | Evidence |
|---|---|---|
| Fix 1: catch `AxeConfigError` in the TUI status collection path, return structured degraded status | PASS | `src/sase/ace/tui/actions/axe_display/_data.py:190-196` catches around `proc.get_axe_status()`, `:211-216` around `load_axe_config()`; `AxeStatusDegradation` dataclass at `_data.py:99-104`; `_invalid_config_status` formats first diagnostic (`_data.py:134-142`). The raise site the plan cites is real: `src/sase/axe/_process_status.py:45` and `:101` (`get_lumberjack_names`) both call `load_axe_config()` inside `get_axe_status()`. |
| Fix 1: Axe pane renders it | PASS | Threaded through `_loaders.py:189-192` → `_render.py:159` → `widgets/axe_dashboard.py:95-101` → `widgets/_axe_dashboard_status.py:186-194` renders `"axe config invalid: …"` in bold red with the auto-refresh countdown, replacing runtime counters. |
| Fix 2: pump-task failure dedup (traceback once per (task-name, exception-signature), then rate-limited counter) | PASS | `src/sase/ace/tui/util/pump_tasks.py:34-58` — `_log_task_failure` keys on `(name, error_type, message)`, `log.exception` on first hit, then one-line `log.error` counter at most every 5 min (`_FAILURE_SUMMARY_INTERVAL_SECONDS=300`, line 21), LRU-bounded at 256 signatures (line 22, 43-44). Wired at `:105`. |
| Read-path only / no event-loop blocking | PASS | Diff adds no writes and no new event-loop work; degraded fallback uses empty `AxeConfig()` so per-lumberjack I/O loops become no-ops. |
| Test: invalid config → degraded status, no raise | PASS | `tests/ace/tui/test_axe_collector.py:86-127` (`test_collector_degrades_invalid_axe_config_to_status`): `get_axe_status` raises → collector returns `degraded_status` with exact message, `load_axe_config` not called again. |
| Test: pump dedup logs once then suppresses | PASS | `tests/ace/tui/test_pump_tasks.py:72-105`: 3 identical failures → exactly 2 log records, exactly 1 with traceback, summary says "repeated failure 2 time(s)". |
| Dashboard render test (bonus) | PASS | `tests/ace/tui/widgets/test_axe_dashboard_status_section.py:215-237`. |

**HEAD integrity:** `git log 4103e9154..HEAD` shows zero commits touching `_data.py`, `pump_tasks.py`, `_axe_dashboard_status.py`, `_process_status.py`, or the three test files. All cited lines verified at current HEAD.

---

## Phase sase-8g.6 "Journal and damp axe fleet restarts" — commit 4103e9154

**VERDICT: COMPLETE** (item 4 is legitimately moot — see below)

| Plan item | Result | Evidence |
|---|---|---|
| Fix 1: bounded JSONL restart journal (source, pid, desired-state, maintenance marker) | PASS | `src/sase/axe/lifecycle_journal.py` — schema-v1 records with `source/reason/orchestrator_pid/desired_state/maintenance` (`_lifecycle_record`, lines ~118-150), 256KB byte cap with lock-serialized atomic compaction (`append_lifecycle_event`), tolerant reader (`read_recent_lifecycle_events`), damper window reader (`read_recent_successful_starts`). |
| Fix 1: coverage of `sase axe start/stop`, `ensure_axe` healing, dev-update restarts | PASS | Start journaled at PID publication: `orchestrator.py:451-458`, source from `SASE_AXE_START_SOURCE` env set by `_process_start.py:65` (`_compose_axe_daemon_env`); CLI start reads same env (`src/sase/main/axe_handler.py:177`). Stop: `_process_stop.py:159` with outcome stopped/partial/not_running/failed. Restart: `_process_restart.py:246`. ensure heals with `desired_state_source="axe ensure"` (`ensure.py:156-158`). dev-update passes `source="sase update"` (`update_handler.py` → `update_restart.py:_call_restart_axe`); ACE actions pass "ace start/stop/restart/startup" (`actions/axe.py`, `_loaders.py:479-481`). |
| Fix 2: stale/dead-owner marker clearing on ensure + orchestrator startup, PID-reuse guard | PASS | `ensure.py:96-99` (`clear_stale_maintenance()` before rate-limit/health decisions), `orchestrator.py:446-449` (startup, before lumberjacks). PID-reuse guard: `maintenance.py:_process_identity` records `start_ticks` (field 22 of `/proc/<pid>/stat`) + `boot_id` (`/proc/sys/kernel/random/boot_id`); `clear_stale_maintenance` clears live-PID markers whose identity mismatches; legacy markers without identity preserved. |
| Fix 3: restart-storm damper (N in M min → back off + single notification naming sources) | PASS | `ensure.py:128-154` — defaults 5 starts / 30 min (`ensure.py:36-37`), returns `rate_limited` without calling `start_fn`, message names sources and journal path. Single notification per episode via sha256 signature marker `ensure_storm_notification.json` (`_ensure_runtime.py:183-240`); notification body names sources + journal (`notifications/senders.py:notify_axe_restart_storm`, lines 259-278). |
| Fix 4: Prometheus bind conflict logged once, non-fatal | N/A — MOOT, documented | The Prometheus exporter and its HTTP bind were deleted before this phase by sase-6k.3/6k.6 (`7ccc4688c` / `55df5a75b`, 2026-07-17, ancestors of the phase commit); `grep -ri prometheus src/` finds no server code at HEAD. The phase plan explicitly records this ("no active bind-conflict path to change… keep that behavior intact", `sase/repos/plans/202607/axe_restart_damper.md:26-28`) and retains the legacy-config regression `tests/telemetry/test_config.py:88` (`test_get_telemetry_config_ignores_legacy_prometheus_block`). This is a sound resolution, not a gap. |
| Test: journal records for start | PASS | `tests/test_axe_lifecycle_journal.py:87-122` — real `Orchestrator.run()` journals `start/started` with env source "ace startup" and clears the dead-owner (pid 99999999) marker at startup. Also byte-cap retention (:33-65) and malformed-row tolerance (:68-84). |
| Test: journal records for stop | PASS | `tests/test_axe_process_stop.py:34-37` — stop event, outcome `not_running`, source "axe stop". Restart journaling: `tests/test_axe_restart.py:106-109` (+ source threaded to stop/start calls, :97-105). |
| Test: ensure-heal attribution | PASS | `tests/test_axe_ensure.py:71-73` — ensure calls start with `desired_state_source="axe ensure"`; combined with the env-handoff test (`tests/test_axe_process_start.py:49-55`) and orchestrator journal test, the ensure-heal→journal chain is fully covered (no single end-to-end test, but every link is asserted). |
| Test: dead-owner marker cleared by `ensure_axe` | PASS | `tests/test_axe_ensure.py:103-129` — live-but-recycled PID identity mismatch, `ensure_axe` clears the marker before the health decision. Maintenance-level: `tests/test_axe_maintenance.py:70-128` (dead pid, recycled live pid, legacy-marker preserved). |
| Test: storm damper threshold + one notification | PASS | `tests/test_axe_ensure.py:132-184` — 3 journaled starts, threshold 3: start_fn would `AssertionError` if called; both polls `rate_limited`; exactly 1 notification listing all three sources, journal path in `files`, second poll gets no notification id; cadence marker still written. |

**Integration with post-epic commits:**
- **Ensure split `2c4a4f0aa`: survived intact.** `ensure.py` kept `clear_stale_maintenance` (line 97), damper block (lines 128-154), and thresholds (36-37); the storm helpers (`recent_starts_for_damper`, `recent_start_sources`, `_restart_storm_signature`, `maybe_notify_restart_storm`, storm marker path) moved verbatim into `src/sase/axe/_ensure_runtime.py:160-240` (bodies byte-identical to the phase commit); timer code moved to `_ensure_timer.py`. Public `__all__` preserved.
- Only two phase-6 files were touched after landing: `orchestrator.py` and `_process_start.py` by `866aea65a` (sase-8g.11 test-state isolation) — the journal append + startup cleanup block is still present at `orchestrator.py:445-458`, and the `AXE_START_SOURCE_ENV` handoff at `_process_start.py:31,65`.
- `lifecycle_journal.py`, `maintenance.py`, `_process_stop.py`, `_process_restart.py`, and all phase-6 test files are untouched since the phase commit.

**Only caveat worth relaying:** epic-plan item 4 (Prometheus) could not be implemented as written because the targeted code was removed by the earlier sase-6k telemetry epic; the phase plan documents the mootness and keeps a regression test proving legacy prometheus config cannot affect startup. If the epic close-out requires literal item-4 delivery, it should be recorded as "resolved-moot" rather than "implemented".

Phases 4 and 6 verified complete — degraded axe-status rendering, pump-task log dedup, the restart journal with source attribution, dead-owner marker clearing with PID-reuse guard, and the storm damper are all confirmed at HEAD, with the logic surviving the ensure-responsibilities split verbatim. The plan's Prometheus bind-conflict item is legitimately moot (that exporter was deleted by the earlier sase-6k telemetry epic before this phase ran, and the phase plan documents that with a regression test). Three verifications remain (phases 2+8, 7, 10+11).

All targeted tests pass at HEAD (111 + 48). Verification complete.

---

# Verification Report: Epic sase-8g phases 2 and 8

## Phase sase-8g.2 — "Retry family-phase agents under the family base name" (48abe26ea)

**VERDICT: complete** — all plan Fix items and Tests implemented in the commit and intact at HEAD.

Fix items:
- **Kill-and-edit seeding normalized via `agent_family_base`** — PASS. `src/sase/ace/tui/actions/agent_workflow/_entry_name_prompts.py:65-68` (`prepare_kill_and_edit_prompt` computes `agent_family_base(agent_name) or agent_name` before `force_name_reuse_in_prompt`).
- **Plain retry path normalized** — PASS. `src/sase/ace/tui/actions/agent_workflow/_entry_relaunch.py:56-66` (`_retry_edit_agent` allocates via `allocate_retry_name(retry_source_name)` with the base name, and passes it as `current_agent_name`).
- **Mobile retry normalized** — PASS. `src/sase/integrations/_mobile_agent_lifecycle.py:74-79` (same normalization; provenance preserved — test asserts `source_agent_name`/`retry_of_agent` keep the `--plan` row name).
- **Validation NOT loosened** — PASS. `src/sase/agent/launch_validation.py:107-113` (`validate_user_agent_name` still rejects `--`); `validate_launch_name_requests` (lines 149-211) was refactored to call the new `_preflight_launch_name_requests` and retains all reservation/clan/family collision checks under the allocation lock — checks were factored out, none dropped. `_launch_body_single.py:178` still runs the full `validate_launch_name_requests([prompt])`.
- **No bypass added for user prompts** — PASS. `SASE_INTERNAL_AGENT_NAME_BYPASS` is set only in `src/sase/agent/_family_attach_launch.py:46` (trusted family-attach launcher); no reference in `_launch_body_impl.py`, `_launch_body_single.py`, or `_mobile_agent_lifecycle.py`.
- **Reorder: syntax validation before wipe** — PASS. `src/sase/ace/tui/actions/agent_workflow/_launch_body_impl.py:65-79` runs `preflight_launch_name_requests(..., allow_force_reuse=True)` (non-mutating syntax check) and returns an error `LaunchTaskOutcome` (recording the failed prompt) before `wipe_names_for_forced_reuse` at line 85. `src/sase/agent/names/_wipe.py` unchanged (wipe remains the destructive op, now unreachable for rejected names).

Tests (all exist at HEAD, all pass):
- Kill-and-edit seeds base `%id`: `tests/ace/tui/test_retry_edit_agent_name.py:425` (`test_kill_and_edit_family_phase_forces_base_name_reuse`, asserts `%id:!sase-8a.3` for row `sase-8a.3--plan`) plus a parametrized force-reuse case at ~line 239.
- Retry-name allocation from a family row: `tests/ace/tui/test_retry_edit_agent_name.py:276` (asserts `allocate_retry_name("sase-8a.3")`); mobile: `tests/test_mobile_agent_kill_retry.py:228` (asserts `allocated_from == ["alpha"]`, launch as `alpha.r0`, source-agent provenance retained).
- Name-syntax rejection performs no wipe: `tests/ace/tui/test_agent_launch_non_blocking.py:378` (`wipe.assert_not_called()`, error outcome with the `--` message); parse-failure no-wipe at :354; preflight unit tests `tests/test_agent_launch_validation.py:216-233`.

Post-epic integration: `git log 48abe26ea..HEAD` on all five phase files is empty — no later refactor touched them. Note: the commit moved `parse_multi_prompt` out of its try/except in `_launch_body_impl.py`, so parse failures now propagate from the task callable instead of falling back — covered by the updated test and still non-destructive; not a plan deviation.

## Phase sase-8g.8 — "Harden fork parent resolution" (0b9ef92f4)

**VERDICT: complete** — both Fix items implemented via the "park on wait machinery" option (the plan's preferred branch), intact at HEAD after the cdb2af023 refactor.

Fix items:
- **Same-transcript parents dedupe silently; textual duplicates raise** — PASS. `src/sase/scripts/agent_chat_from_name.py:156-170` raises "repeated parent argument ... already requested as parent N" only for textually identical user args; `:183` routes resolved sources through `_coalesce_fork_sources` (`:186-215`), which keeps the first occurrence of each canonical transcript path (agents dropped, clan/family members filtered, empty containers omitted). The old `transcripts()` cross-source duplicate check that raised was deleted.
- **Incomplete-clan/agent `#fork` parks pre-workspace** — PASS, via the wait-machinery branch:
  - `#fork` counts as a deferred-start directive: `src/sase/xprompt/_directive_scan.py:51-59` → `src/sase/agent/launch_cwd_agents.py:493` launches with `deferred_workspace=has_wait` (placeholder workspace, no real claim at launch).
  - Fork parents become wait names: `src/sase/axe/run_agent_directives.py:180-187` (`fork_agent_names(fork_reference_prompt)` appended to `wait_names`).
  - Fork expansion deferred through every launch-analysis boundary via `LAUNCH_DEFERRED_XPROMPT_NAMES = frozenset({"fork"})` (`src/sase/xprompt/processor.py:68`), threaded through `_launch_body_single.py`, `launch_cwd_agents.py`, `launch_request_planning.py`, `multi_prompt_launch_plan.py`, `run_agent_directives.py`, and `preprocess_prompt_xprompts`.
  - Runner ordering at HEAD: `src/sase/axe/run_agent_runner.py:312` `wait_for_dependencies` → `:374` `expand_deferred_launch_xprompts` → `:380` `wait_for_runner_slot` → `:400` `claim_deferred_workspace`. Clan/family wait targets are supported by the wait index (`src/sase/core/wait_dependency_resolution/_index.py:46,222-247`), so an incomplete clan parks on the same machinery as `%w` and fork resolution runs only after admission, before slot claim and real workspace claim. `expand_deferred_launch_xprompts` (`src/sase/axe/run_agent_runner_setup.py:234-268`) restricts embedded expansion to the fork set and rejects post-steps.
  - The plan's "minimally, fail fast ... with a message naming incomplete members" alternative was not needed; parking (the primary option) is implemented. One residual: a `#fork` of a name that will *never* exist parks indefinitely like a `%w` typo — the plan itself lists wait-target existence validation as a deferred follow-up, so this is consistent, not a gap.

Tests (all exist at HEAD, all pass):
- Same-transcript pair → one source: `tests/test_agent_chat_from_name.py:265`; repeated textual parent raises atomically: `:285`; family/clan overlap coalescing: `tests/test_agent_chat_from_name_family.py:276` (+ overlapping later-member tests), `tests/test_agent_chat_from_name_clan.py:137`.
- Incomplete clan parks pre-workspace: `tests/test_axe_run_agent_runner_deferred_workspace_flow.py:222` (moved there by test-split commit 71c5e2a05; asserts event order `["wait", "fork", "gate", "claim", "run"]`).
- Complete clan still works: `tests/test_fork_workflow.py:269` (`expand_deferred_launch_xprompts` on a completed clan injects both member prompts).
- Defer semantics: `tests/test_snippet_references.py` (fork deferred while other refs expand, including refs introduced recursively); `tests/test_run_agent_runner_setup.py:140` (embedded expansion limited to `{"fork"}`).

Post-epic integration: cdb2af023 split `run_agent_directives.py` into `run_agent_directive_identity.py`/`run_agent_directive_metadata.py`; the fix survived — `fork_reference_prompt` fallback at `run_agent_directives.py:122-126`, fork wait-target loop at `:180-187`, and `fork_reference_prompt` passed to the identity module (`run_agent_directive_identity.py:51,65` for resume detection). No other post-epic commit touched the phase-8 files.

Test execution: all 159 tests in the files above pass at current HEAD (111 passed + 48 passed).

Phases 2 and 8 verified complete — retry/kill-and-edit/mobile seeding all normalize to the family base name without loosening validation, rejected launches no longer wipe registry state, same-transcript fork parents coalesce while textual duplicates still raise, and incomplete-clan forks now park on the standard wait machinery before claiming a workspace. All 159 related tests pass at HEAD. Two verifications remain (phases 7 and 10+11).

VERDICT: complete, with two documented nuances (neither blocks landing; both are interpretation-level, not regressions).

Note: the sibling Rust repo `../sase-core` does not exist in this environment; item (d) was verified from the Python side via the installed `sase_core_rs` 0.8.0 binding.

Per plan-item results:

(a) Union-merge of append-only streams — PASS. The commit chose the plan's preferred "explicit conflict resolution" option (no `merge=union` gitattribute exists anywhere in src/sase). At HEAD, `resolve_bead_conflicts` reads base/local/upstream index stages of each conflicted `beads/events/streams/*.jsonl` and merges via the Rust `bead_merge_event_streams` binding (`src/sase/bead/conflict_resolver.py:77-101`, facade at `src/sase/core/bead_conflict_facade.py:11-18`), then reconstructs `issues.jsonl` and the manifest from the merged streams (`conflict_resolver.py:88-98`). Note the merge machinery itself predates this commit (introduced in 74d0820af); 24d42d381's contribution here is fixing the beads-dir misresolution that made it never fire on the observed rollback path — `push_sdd_store_after_commit` now passes `store.kind_root("beads")` instead of `store.repo_root` (`src/sase/sdd/_commit_store.py:322-333`) and `resolve_beads_dir` validates canonical relpaths (`conflict_resolver.py:138-157`). This directly explains the logged `non-bead conflicts remain: beads/events/streams/sase-84.jsonl, beads/issues.jsonl` evidence.

(b) Manifest recount as logged repairable condition — PASS with nuance. `repair_event_manifest_after_integration` (`src/sase/sdd/_bead_manifest_repair.py:29-178`) runs inside `_successful_integration` on every integration outcome, including the no-op already-ancestor path (`src/sase/sdd/_repository_integration.py:130-143, 282-305`), emits `manifest_repair` events (repaired/noop/invalid_stream), and commits `chore(beads): repair event manifest`. Nuance: repair only runs in integration paths. I probed store-open directly: a mismatched manifest still raises `ValueError: validation: bead event manifest stream_count mismatch: 5 != 1` at `BeadProject` open (Rust-side validation; error string confirmed in `sase_core_rs.abi3.so`). Post-fix, sync can no longer commit a mismatched manifest (repair failure rolls the whole integration back), and pre-existing mismatches heal on the next sync (`sase` entry schedules refresh, `src/sase/main/entry.py:124-126`; `refresh_current_bead_store` at `src/sase/bead/sync.py:422-452`), so the production launch-blocker class is fixed — but a mismatch reached without an intervening sync (e.g. non-sync corruption, or a launch racing the async refresh) still hard-blocks at open. Defensible as validation, but it is not a literal "repair at validation time".

(c) issues.jsonl / robust rollback — PASS. issues.jsonl conflicts are actually resolved by store-level reconstruction from the merged streams (`_is_mergeable_bead_path` includes it, `conflict_resolver.py:169-173`; reduction at :88-89), which exceeds "leave to retry/rebase" consistent with intent. Rollback robustness: `_abort_and_verify` guarantees never-mid-rebase (`rebase --abort` when active, plus the new `reset --hard <starting.head>` fallback for completed-but-invalid integrations, `_repository_integration.py:375-412`) with verified restoration against the starting snapshot; failure to verify returns UNRECOVERABLE rather than silently leaving state.

(d) Rust core boundary — PASS. Recount/repair implemented in Rust: `bead_repair_event_store_manifest` exists in the installed binding (verified via import: `['bead_event_store_manifest', 'bead_merge_event_streams', 'bead_read_event_store', 'bead_reduce_event_streams', 'bead_repair_event_store_manifest']`), exposed through `src/sase/core/bead_conflict_facade.py:30-32`. Python only stages/commits the repaired file and guards path/tracking invariants.

Tests — PASS with one fidelity gap. `tests/test_bead/test_sync_conflict_regressions.py` exists at HEAD unchanged since the commit; all 6 tests pass (ran: `6 passed in 2.03s`). `test_generic_sdd_push_reconciles_same_stream_and_derived_files` (line 665) is exactly the plan's scenario 1: two clones append to the same stream, sync unions both (5 lines), manifest recount `stream_count == 1`, no rebase state or unmerged paths remain, both writers' data visible in a fresh clone. `test_clean_rebase_repairs_stale_manifest_and_repeated_sync_is_noop` (line 752) covers logged repair + idempotent noop. Fallback coverage: `test_invalid_same_stream_aborts_to_exact_starting_state` (line 886), `test_mixed_bead_and_non_bead_conflicts_abort_exactly` (line 928), `test_clean_rebase_with_invalid_stream_resets_completed_integration` (line 959) all assert exact starting-state restoration and no mid-rebase. Gap: no test constructs a literal conflicting `rollback_work_launch` commit; coverage is via `push_sdd_store_after_commit` (the exact function the rollback commit path calls through `auto_commit_bead_store`), so the code path is exercised but not under the rollback framing the plan named.

Integration with post-epic commits — clean. `git diff 24d42d381 HEAD` is empty for `conflict_resolver.py`, `bead_conflict_facade.py`, `_bead_manifest_repair.py`, and the regression test file. The only later touch is 5c93569d8, which split `_repository_transaction.py` into `_repository_integration.py`/`_repository_health.py`/`_repository_types.py`; I read the split files and all commit logic (manifest repair hook, verify-ancestor, dirty-tree check, reset-hard rollback fallback) is preserved intact, with `beads_dir`/`event_logger` still threaded through the public wrapper (`src/sase/sdd/_repository_transaction.py:44-81`).

Phase 7 (bead stream sync conflicts) verified complete — the union-merge fires correctly now that the beads-dir misresolution is fixed, manifest recount/repair lives in Rust behind the `sase_core_rs` binding per the core boundary, and rollback can never leave the repo mid-rebase. Two interpretation-level nuances noted (manifest repair runs on sync/integration paths rather than at store-open validation, and the rollback-conflict scenario is covered via the shared push path rather than a literally-framed rollback test) — neither is a regression or landing blocker. One verification remains (phases 10+11).

All verification complete. Final report:

---

# Phase sase-8g.10 "Bound and harden log sinks" — commit 350af961b

## VERDICT: complete

(All paths relative to `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/` unless noted; line numbers are current HEAD, which is byte-identical to the commit — `git log 350af961b..HEAD` over every touched source file is empty.)

**Fix 1 — rotate previously-unrotated sinks (single `.1` generation):** PASS
- Shared rotation lives in `src/sase/logs/_bounded.py:103-122` (`_rotate_if_needed_locked`: unlink `.1`, `os.replace`).
- `runs.jsonl`/`events.jsonl`: `src/sase/logs/run_log.py:55-60` (`_append_jsonl` → `append_jsonl_record`), called at :101 and :120.
- `dev_update.jsonl`: `src/sase/dev_update/journal.py` (`append_dev_update_journal` → `append_jsonl_record` with `SASE_DEV_UPDATE_JOURNAL_MAX_BYTES`).
- `tui_agent_loads.jsonl` (+ other tui telemetry sinks): `src/sase/logs/tui_telemetry.py` `_append_jsonl` → `append_jsonl_record`.
- `tui_toasts.jsonl`: `src/sase/logs/toast_log.py` `_append_record` → `append_encoded_line_locked` + compaction under the same lock.
- `tui.log`: PASS with a note — rotation was NOT added by this commit; a `RotatingFileHandler` (2 MiB, backupCount=3) has existed since 1feff1109 (2026-06-17) at `src/sase/ace/tui/log_setup.py:44-47`. The plan's evidence (1.6 MB "grows forever") was stale — the file was simply under the 2 MiB threshold. The phase adds only the regression test. Behavior holds at HEAD.

**Fix 2 — single O_APPEND write / lock; torn-line-tolerant readers:** PASS — `src/sase/logs/_bounded.py:82-100`: one `os.write` on an `O_APPEND` fd (:92) while a sibling `.lock` flock is held (`log_file_lock` :67); short writes raise. Readers: `src/sase/logs/collectors.py:217-219` and :245-247 skip `json.JSONDecodeError` lines.

**Fix 3 — hook capture cap head+tail with elision marker:** PASS — `src/sase/ace/hooks/output_capture.py:11-13` (200 KB head / 300 KB tail, `=== SASE HOOK OUTPUT ELIDED: N bytes omitted ===`), tail preserved byte-exact; invoked from `check_hook_completion` at `src/sase/ace/hooks/execution.py:321` only after the completion marker is present and after metahook matching sees the full output. Design note (not a gap): captures are compacted on completion, not truncated while streaming, so a running hook can still grow until it finishes — the 17.9 MB evidence file was a completed capture, so this satisfies the plan's target.

**Fix 4 — GC of stale `.tmp` siblings >1 day in the writer helper:** PASS — `src/sase/core/atomic_temp.py:10-13` (`reap_stale_atomic_temps`, 24 h), called from `src/sase/notification_gates/durability.py:71` and `src/sase/notifications/pending_actions.py:481`. The evidence's `.notifications.jsonl.<pid>.<ts>.tmp` orphans come from the Rust store writer, covered by a companion sase-core commit `f304499 fix(notifications): reap stale atomic temp files (sase-8g.10)`: `reap_stale_temp_siblings` at `crates/sase_core/src/notifications/store.rs:559` (24 h `STALE_TEMP_MAX_AGE` :18), invoked from the rewrite path at :530 (verified in the sase-core checkout opened via `sase repo open`, at `sase/repos/linked/sase-core/`).

**Tests (all present at HEAD, read):**
- Rotation trigger: `tests/dev_update/test_journal.py:175`; `tests/logs/test_toast_log.py:115`; `tests/logs/test_tui_telemetry.py:11`; `tests/ace/tui/test_tui_log_setup.py:81`; `tests/logs/test_bounded_writer.py:14` (single-backup semantics). PASS
- Concurrent-append stress, zero torn lines: `tests/logs/test_run_log.py:102` — 2 forked processes × 100 records, asserts 200 parseable JSON lines. PASS
- Truncation head/tail/marker: `tests/test_hook_output_capture.py:22` (+ idempotence, running-capture untouched :52, metahook-sees-full-output :101). PASS
- Tmp GC leaves fresh temps: `tests/test_notification_gate_durability.py:12`, `tests/test_pending_actions.py:48` (fresh, unrelated-target, and near-match names all preserved). PASS
- Torn historical line tolerated: `tests/logs/test_collectors.py:133`. PASS

**Integration:** no post-epic commit touches any phase 10 file.

---

# Phase sase-8g.11 "Keep tests out of production state" — commit 866aea65a

## VERDICT: complete

**Fix 1 — hard guard at telemetry write boundary (raise in tests, warn-once no-op otherwise):** PASS — `src/sase/telemetry/_registry.py:135` calls `assert_test_state_write_isolated(store_path, category="telemetry")` before samples are drained or the Rust binding is touched. Guard: `src/sase/core/state_write_guard.py:38` (raising) and :56 (`best_effort_test_state_write_allowed`, warn-once per category+target). Real home is resolved via `pwd.getpwuid` (:35), deliberately not trusting `HOME`/`Path.home`, so tmp-fixture homes pass and only writes under the real `~/.sase` are refused.

**Fix 2 — same guard shape on axe crash-loop notify path / call-time writers:** PASS — `src/sase/axe/orchestrator.py:244` (`_surface_crash_loop` returns before `append_error`/notification send); 44 guard call sites across 14 files at HEAD (`state.py` `atomic_write_json`, `_state_lumberjack.py` `append_bounded_log`/pid files, `_state_chops.py`, `_state_scheduler.py`, `chop_agents.py`, `chop_script_context.py`, `chop_script_runner.py`, `lumberjack.py`, `runner_pool.py`). `src/sase/axe/_process_start.py` preserves `PYTEST_VERSION` into daemon envs so spawned children stay guarded.

**Fix 3 — explicit one-time cleanup command (delete test-workflow/test-provider/fakey + vacuum, never implicit):** PASS — `sase telemetry cleanup-test-data` (`src/sase/main/parser_telemetry.py:20`, dispatch in `src/sase/main/telemetry_handler.py`); always previews, refuses deletion without `-y/--yes` (exit 2); exact labels in `src/sase/telemetry/maintenance.py:10-13` (`test-provider`, `fakey`, `test-workflow`); mutating run itself re-checks the isolation guard (:25). Vacuum is in the Rust companion commit `f659642 feat(telemetry): add exact-label cleanup API (sase-8g.11)`: `crates/sase_core/src/telemetry/store.rs:194` runs `VACUUM` after a non-empty transactional delete across samples/rollup_5m/rollup_1h. Only reachable from the CLI — nothing invokes it implicitly.

**Fix 4 — leaking fixture (frozen 20260316_120000 runner instance):** PASS — the frozen instance lives in `tests/_axe_run_agent_runner_retry_helpers.py:81`/`:151`; the commit's fix at :170-182 flushes metrics while the per-test `SASE_HOME` is still active, then `_reset_for_tests()` unregisters the runner's atexit flush so it can never fire after fixture teardown. Any future leak now raises via Fix 1.

**Tests (all present at HEAD, read):**
- Unisolated pytest telemetry refusal: `tests/test_state_write_guard.py:28` — raises `RuntimeError` matching "Set SASE_HOME" before drain, `telemetry_record_batch` never called, real-home tree never created. PASS
- Isolated homes still record: same test, second half — isolated store config flushes 1 sample through the binding. PASS
- Warn-once no-op: `tests/test_state_write_guard.py:67` — two writes, exactly one refusal log, no real-state touch. PASS
- Crash-loop guard: `tests/test_state_write_guard.py:96` — no `append_error`, no notification. PASS
- Cleanup removes only test-labeled samples: `tests/telemetry/test_cli_cleanup_test_data.py:77` — end-to-end against a real sqlite store; 3 exact-label rows deleted, near-miss label `test-provider-near-miss` preserved (4→1 rows), repeat run deletes 0. Plus refuses-without-yes (:47) and dry-run-never-mutates (:63). PASS

**Integration:** the two post-epic axe refactors (`cdb2af023` split `run_agent_directives.py`, `2c4a4f0aa` split `ensure.py`) touched files that carry no phase 11 guards; all guard call sites and the guard/telemetry/cleanup modules are unchanged since the commit. No conflicts found.

---

**Summary:** both phases are genuinely complete against the plan sections in `sase/repos/plans/202607/audit_24h_fixes.md`, hold at HEAD, and have the required tests. The only findings are informational: (a) tui.log rotation predated the epic (plan evidence was stale; the phase added only the regression test), (b) hook captures are bounded at completion rather than during streaming, and (c) two plan sub-behaviors (notifications tmp GC, cleanup VACUUM) landed as companion sase-core commits f304499 and f659642, both verified in that repo.

All seven verification agents are done: **all 11 phases verified genuinely complete at HEAD**, with tests passing and the epic's logic intact through the post-epic refactors. The only findings were informational (a moot Prometheus item documented in the phase plan, stale plan evidence about tui.log rotation, two sub-behaviors landed as companion sase-core commits). No remaining work surfaced, so I'm proceeding directly to landing: close the epic, run symvision, mark the plan done.

Epic sase-8g is landed. Summary of the full close-out:

**Verification (step 1)** — Seven parallel review agents checked every phase's commit against the plan's fix and test requirements, and re-read the code at current HEAD. All 11 phases are genuinely complete: the fresh-read locked hooks transforms (.1), family-base-name retry seeding with non-destructive rejected launches (.2), the three runner-slot wait fixes plus admission docs (.3), degraded axe-status rendering and pump-log dedup (.4), SDD clone snapshot-then-reset self-heal (.5), the restart journal/damper with PID-reuse guard (.6), Rust-side stream union-merge and manifest repair (.7), fork-parent dedupe and pre-workspace wait parking (.8), display/help-binding gaps (.9), bounded atomic log sinks (.10), and the test-state write guard plus `sase telemetry cleanup-test-data` (.11). All cited tests exist and pass. Informational notes only: phase 6's Prometheus item was already moot (the exporter was deleted by the earlier sase-6k epic, documented in the phase plan), tui.log rotation predated the epic (the plan's evidence was stale), and two phase-10/11 sub-behaviors correctly landed as companion sase-core commits.

**Integration (step 2)** — ~18 non-epic commits landed since the epic started. The four refactors that split epic-touched modules (axe ensure, run-agent directives, SDD recovery/transaction) preserved the epic's logic verbatim — each was explicitly diff-checked. The sase-8f/8d feature commits introduce no new log sinks or state writers that should adopt the epic's rotation/guard helpers, and the two docs passes don't contradict the epic's doc additions. No integration work was needed.

**Landing (step 3)** — `sase bead close sase-8g` succeeded; `just symvision` came back clean (no stale sase-8g whitelist entries, no unused symbols); the plan file `202607/audit_24h_fixes.md` in the plans sidecar now has `status: done` (opened via the repo skill; the sidecar's sync machinery will commit it). The primary workspace is clean, so `just check` isn't required.

One unrelated observation worth knowing: the symvision run warned that the linked sase-core checkout in this workspace is at 0.8.0 while `pyproject.toml` requires `sase-core-rs>=0.11.0` — a stale linked checkout, not an epic issue, but a `just install`/pull of sase-core may be due in workspaces that run the Rust-backed tests.

The uncommitted change in the plans sidecar is mine from this session — the `status: done` frontmatter edit to `202607/audit_24h_fixes.md`. I'll commit it with the commit skill.

The diff is exactly the one-line frontmatter change. Writing the commit message and committing.

Committed. The finalizer's flagged change was mine — the `status: wip` → `status: done` frontmatter edit to `202607/audit_24h_fixes.md` from closing epic sase-8g. I committed it in the plans sidecar via the `/sase_git_commit` skill as `chore(plans): mark audit_24h_fixes plan done (sase-8g)`, using `-f` for just that file. The commit dispatched through `create_commit` successfully, and `git status --short --branch` now shows the repo clean and in sync with `origin/main` (both listed entries pointed at the same checkout, so the single commit covers them). That was the last outstanding item — epic sase-8g is fully landed.
