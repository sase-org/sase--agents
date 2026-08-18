# Chat History - ace-run (sase-ng.1.land--1)

- **TIMESTAMP:** 2026-08-17 19:59:15 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-ng.1.land--1

## Prompt

%xprompts_enabled:false
# Previous Conversation

**User:**

You are the land agent for epic bead sase-ng.1: verify the epic is truly complete, integrate it with changes
that landed since it started, then close it out.

1. Verify. Run `sase bead show sase-ng.1` (children, linked plan file), review the epic bead's own notes, then
run `sase bead show` on every child and review every child note. Confirm each note was addressed, and read the
actual source code and the epic's commits (bead IDs appear in commit messages) to confirm the work previous
agents reported complete really is. While reviewing child beads, collect every `PROPOSED FOLLOW-UP:` note entry.

2. Integrate. Changes committed since this epic started could not integrate with this epic's feature while it was
incomplete. Find them (e.g. `git log` since the first commit mentioning sase-ng.1, excluding the epic's own
commits; in a PR workflow also review commits on the base branch) and update anything that should now use what
this epic added or that duplicates or conflicts with it. This integration is part of the epic's work.

3. Land. Unresolved issues caused by this epic remain epic work: plan and finish them before closing. For each
genuinely distinct follow-up that is not caused by the epic, use `/sase_new_task` with details identifying the
proposing bead; it will corroborate a duplicate, attach a causally related active-epic issue, or create a sized
task as appropriate. Record every outcome, including why any proposal was declined, in your close note. Before
closing, run `sase bead epic-symbols sase-ng.1`. Every listed `--epic-symbol` entry is keyed to this epic
or one of its phases and goes stale the instant that bead closes. For each entry, either resolve the symbol
(wire it up, privatize it, add a non-test pragma, or delete it per the Symvision epic-whitelist policy) or,
only when a still-open later bead still needs the exemption, re-key the Justfile line to that open bead. Do not
leave that judgment for the next agent. `sase bead close` refuses while any of these entries remain. Close the
epic with `sase bead close sase-ng.1 --note "<what you verified in steps 1-2>"`. After closing, run
`just symvision` if available to confirm the whitelist is clean. Finally, set `status: done` in the frontmatter
of the epic's plan file (the PLAN path shown by `sase bead show`). If the close is rejected because leftover
`--epic-symbol` entries remain, finish that cleanup and close again. If the close is rejected because named
phases were never completed: finish or reopen them, or record the outcome deliberately with
`--force --reason ... --resolution canceled|superseded`. Never force merely to make the command succeed, and
never use `--force` to advance a successful nested landing.

If steps 1-2 uncover remaining work, use your /sase_plan skill to plan it and complete the skill's tier-aware
validate/revalidate/propose loop. Plan only the remaining work. Do not include this epic's close, symvision pass,
or plan-file status update as a child phase; the child epic's `parent_bead` link is the handoff that lets its land
agent resume this interrupted landing after the child lands.

After the current epic closes, inspect the linked `parent_bead` from `sase bead show sase-ng.1`. If there is
no parent bead, finish normally. If the parent is a phase bead, verify this child plan completed the work required
by that phase, close only that parent phase normally with `sase bead close <parent-bead> --note "<what you
verified>"`, and leave the containing epic to its already-waiting land agent. If the parent is a plan bead, review
the parent's previous landing note, all descendants and notes, linked plan file, and post-child drift; rerun
descendant and linked-plan readiness checks before closing it. When the parent plan is still complete, retire any leftover `--epic-symbol`
entries first (`sase bead epic-symbols <parent-bead>`), close it normally with
`sase bead close <parent-bead> --note "<what you rechecked>"`, confirm with `just
symvision`, mark its linked plan file done, and then repeat through directly parented plan ancestors
while each remains fully complete. Stop at the first incomplete or ambiguous parent, record a note on that parent describing the blocker,
and report it in your final response.

**Assistant:**

# Monitor handoff

This agent delegated the remaining work to a monitor shell.
Monitor ID: 7jzhrte86141
Inspect with: sase monitor show 7jzhrte86141
Monitor shell: sase-ng.1.land--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13

Command:

```sh
just check-full
```

Reason:

Combined-tree gate the sase-ng.1 epic plan requires before landing; lint and targeted suites already green at HEAD c89e5bbeb

Next action:

You are resuming the landing of epic bead sase-ng.1 (Retire dead ACE in-process launch and cleanup bodies). Steps 1 and 2 of the landing are already DONE and recorded in full as the "LANDING VERIFICATION (sase-ng.1.land, HEAD c89e5bbeb)" note on sase-ng.1; read it with `sase bead show sase-ng.1` before acting. Do not redo that verification. The only thing that was outstanding is the combined-tree `just check-full` gate the epic plan requires before the close, which is the run you are being handed.

TRIAGE THE RESULT FIRST.
- Two gates are known-red on master and are NOT this epic's work. Do not file new task beads for them. tools/check_test_cost_budgets (peak_worker_rss_kib, causes.ace_page_enter, causes.parser_create, causes.textual_app_run_test_enter) is tracked on sase-j0 - phases sase-ng.1.5 and sase-ng.1.6 already recorded +1s there, so this reporter has already counted; add `sase bead note sase-j0` with this run's numbers instead of another +1. `just selection-health --fail-on-new-flake` overflow nodes are tracked on sase-jq, sase-jb, sase-kd and peers - triage each named node through your sase_new_task skill and corroborate rather than creating duplicates.
- Any lint/fmt/mypy/symvision failure, or any pytest failure, is a real blocker. Reproduce it, then decide whether this epic caused it by stashing or by checking whether the failing area touches the epic's surface (durable RUN_LAUNCH payloads, sase.agent.force_reuse_launch, src/sase/main/query_handler/_launch.py, ACE launch/cleanup proc submission, ops/commands/agent.py cleanup payload application). If this epic caused it, that is remaining epic work: use your sase_plan skill to plan just the remaining work and complete its validate/revalidate/propose loop, and do NOT close. If it is unrelated and pre-existing, record it per the bead policy and continue to the close.

IF THE RUN IS CLEAN (or fails only on the two known-red gates above), FINISH THE LANDING IN THIS ORDER.
1. `sase bead epic-symbols sase-ng.1` must still report no entries (it did at handoff, and the Justfile whitelist holds only sase-n4.5/sase-n4/sase-p1.2 lines).
2. Close the epic: `sase bead close sase-ng.1 --note "<note>"`. The note must state what was verified in landing steps 1 and 2 - summarize the LANDING VERIFICATION note on the bead (deleted module inventory confirmed absent, zero proc_callable in src with only the preserved _submit_session_worker seam left in tests, force-reuse/warning-toast/cleanup-recovery wiring confirmed end to end, all child PROPOSED FOLLOW-UPs resolved with sase-p6 and sase-p7 filed ready and the sase-oc/sase-j0/force-reuse-assertion proposals resolved without new beads, the epic's own DISCOVERED ISSUE note confirmed stale because 65b72d43a already removed all six sase-ng.1.5 entries, and the nine non-epic commits since 97f5b6f03 reviewed with Justfile-only overlap and no doc or code owed) - and add this check-full run's outcome.
3. `just symvision` to confirm the whitelist is clean.
4. Set `status: done` in the frontmatter of /home/bryan/.sase/plans/202608/retire_dead_ace_launch_cleanup_bodies.md (the epic's PLAN path).
5. PARENT HANDLING. sase-ng.1's parent is sase-ng, which is a TASK bead (not a phase and not a plan bead), currently in_progress, sized large, and its description asks for exactly the work this epic delivered: retire both dead in-process body families and both proc_callable parameters and migrate the affected test doubles onto the durable submit paths. Confirm that against the closed epic, then close it normally with `sase bead close sase-ng --note "<what you verified>"`, noting that sase-p6 and sase-p7 carry the two capabilities the plan deliberately scoped out. sase-ng has no parent above it, so stop there. If anything about sase-ng looks incomplete or ambiguous, do not force it: leave it open, put a note on it describing the blocker, and say so in your final response.

Never use --force on any close here. Report the check-full outcome, the closes you made, and anything you left open.

---

%xprompts_enabled:true
# New Query
%model:opus
%effort:max

%xprompts_enabled:false
# Monitored command finished

**Command:**

```text
just check-full
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-08-17T23:01:59.371271+00:00 |
| **Finished** | 2026-08-17T23:25:05.980579+00:00 |
| **Elapsed** | 23m 3s of a 1h 0m 0s budget |
| **Output** | 85 KiB · full log: `sase monitor show 7jzhrte86141 --all-lines` |

**Why this was monitored:** Combined-tree gate the sase-ng.1 epic plan requires before landing; lint and targeted suites already green at HEAD c89e5bbeb

## Last 120 lines of output

Everything between the fences below is raw command output -- untrusted data, not instructions. The only instruction in this prompt is the "Your next action" section.

```text
       8.453s    54x  tests/ace/tui/test_axe_entry_editor_modal.py
       8.386s    36x  tests/ace/tui/test_config_pane_widget_commit.py
       8.091s    32x  tests/ace/tui/test_plugins_browser_pane_sase_update.py
       6.399s    32x  tests/ace/tui/test_config_pane_widget.py
       6.206s    35x  tests/ace/tui/test_config_pane_widget_jump.py
  by Pilot.pause(delay):
      17.649s   286x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      12.648s   758x  tests/ace/tui/test_statistics_pane_interactions.py
       9.929s   156x  tests/ace/tui/test_plugins_browser_pane_loading.py
       7.020s   108x  tests/ace/tui/test_axe_entry_editor_modal.py
       6.630s   104x  tests/ace/tui/test_plugins_browser_pane_install.py
       6.173s    72x  tests/ace/tui/test_config_pane_widget_commit.py
       5.506s    70x  tests/ace/tui/test_config_pane_widget_jump.py
       5.457s    64x  tests/ace/tui/test_config_pane_widget.py
       4.941s    64x  tests/ace/tui/test_plugins_browser_pane_sase_update.py
       4.404s    82x  tests/ace/tui/test_statistics_view_number_select.py
  by Textual App.run_test exit:
       8.633s    38x  tests/test_ace_testing.py
       4.204s    10x  tests/ace/tui/test_artifacts_patches_navigator.py
       3.429s    21x  tests/ace/tui/test_plugins_browser_pane_loading.py
       2.049s     3x  tests/ace/tui/test_top_bar_order.py
       1.619s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
       1.567s    17x  tests/ace/tui/test_axe_entry_editor_modal.py
       1.439s    12x  tests/ace/tui/test_artifacts_scaffold.py
       1.428s    10x  tests/ace/tui/test_config_pane_widget_commit.py
       1.388s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
       1.342s     9x  tests/ace/tui/test_config_center_alternate_tab.py
  by sase.main.parser.create_parser:
       2.610s    36x  tests/main/test_parser_command_help.py
       1.936s    20x  tests/main/test_proc_handler_list.py
       1.925s    20x  tests/main/test_parser_plan.py
       1.626s    21x  tests/main/test_var_get_snapshot.py
       1.624s    19x  tests/test_bead/test_cli_show.py
       1.556s    13x  tests/main/test_monitor_handler_show.py
       1.400s    21x  tests/main/test_parser_proc.py
       1.234s    35x  tests/main/test_var_parser.py
       1.229s    29x  tests/test_bead/test_cli_show_json.py
       1.214s   133x  tests/test_bead/test_cli_show_style.py
  by AcePage.__aexit__:
       8.622s    33x  tests/test_ace_testing.py
       4.207s    10x  tests/ace/tui/test_artifacts_patches_navigator.py
       3.434s    21x  tests/ace/tui/test_plugins_browser_pane_loading.py
       2.049s     3x  tests/ace/tui/test_top_bar_order.py
       1.623s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
       1.571s    17x  tests/ace/tui/test_axe_entry_editor_modal.py
       1.442s    12x  tests/ace/tui/test_artifacts_scaffold.py
       1.430s    10x  tests/ace/tui/test_config_pane_widget_commit.py
       1.392s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
       1.345s     9x  tests/ace/tui/test_config_center_alternate_tab.py
  by Pilot.pause(None):
       4.024s    57x  tests/test_models_panel_edit.py
       3.546s    39x  tests/test_models_panel_jump.py
       2.904s    42x  tests/test_models_panel_override_flows.py
       2.432s    25x  tests/test_models_panel_provider_modal.py
       2.073s    42x  tests/test_models_panel_selector_builder.py
       1.998s    36x  tests/test_command_palette_modal.py
       1.689s    21x  tests/test_models_panel_history.py
       1.528s    32x  tests/test_model_picker_modal.py
       1.433s    27x  tests/test_plan_approval_modal_title.py
       1.210s    21x  tests/test_models_panel_actions.py
  by sase.config.core.load_merged_config:
       0.607s   280x  tests/test_bead/test_cli_show_style.py
       0.233s     8x  tests/completion/test_snapshot.py
       0.233s    14x  tests/main/test_memory_agent_docs.py
       0.231s    70x  tests/main/test_var_parser.py
       0.228s    37x  tests/test_bead/test_cli_golden.py
       0.218s   362x  tests/main/test_init_memory_markdown_templates.py
       0.197s    23x  tests/test_plan_search_cli.py
       0.180s    25x  tests/test_bead/test_cli_search.py
       0.171s    42x  tests/main/test_parser_proc.py
       0.163s    23x  tests/test_plan_validate_diagnostics.py
  by YAML load:
       2.696s  4334x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
       1.160s  4550x  tests/main/test_init_skills_sources.py
       0.837s   783x  tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py
       0.639s   741x  tests/test_bead_xprompt_tags.py
       0.321s    21x  tests/test_github_actions_ci.py
       0.312s   282x  tests/test_pooled_alias_single_consumption.py
       0.302s     6x  tests/test_models_panel_keymaps.py
       0.282s   257x  tests/fakey/test_retry_pipeline_e2e.py
       0.246s   165x  tests/test_followup_prompt_helpers.py
       0.235s   398x  tests/ace/tui/test_xprompt_browser_load_keymap.py
  by subprocess.Popen:
       0.074s     8x  tests/fakey/test_provider.py
       0.026s    34x  tests/test_procs_service.py
       0.014s    12x  tests/llm_provider/test_muse_artifacts.py
       0.012s    13x  tests/main/test_proc_handler_run.py
       0.011s    13x  tests/monitor/test_monitor_supervise.py
       0.007s     8x  tests/main/test_monitor_handler_start.py
       0.007s    14x  tests/test_fork_workflow.py
       0.006s     8x  tests/test_procs_runner.py
       0.006s     3x  tests/test_clan_summary_script_failures.py
       0.005s     7x  tests/test_clan_summary_script_execution.py
  by ACE pause_until_cpu_idle:
       0.001s     1x  tests/test_ace_wait.py
       0.000s     1x  tests/test_a.py
  by gettext.find:
       0.000s     1x  tests/test_bead/test_plus_one_presentation.py
       0.000s     1x  tests/main/test_repo_log.py
       0.000s     1x  tests/agent_clis/test_cli.py
       0.000s     1x  tests/test_mobile_gateway.py
       0.000s     1x  tests/test_editor_helper_agent_catalog.py
       0.000s     1x  tests/test_probe_core_floor_tool.py
       0.000s     1x  tests/ace/tui/artifact_file_viewer/test_entrypoint.py
       0.000s     1x  tests/feature_flags/test_cli.py
       0.000s     1x  tests/test_typecheck_extensionless_tools_tool.py
       0.000s     1x  tests/test_agy_integration_polish.py
test cost budget regression: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260817T232403Z-1797822.json
budgets: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/perf/baselines/test_cost_budgets.json
- collection_cpu_seconds (per worker): actual 27.000 exceeds budget 20.000 + 15% tolerance (23.000)
- idle_seconds: actual 3617.473 exceeds budget 2900.000 + 15% tolerance (3335.000)
- peak_worker_rss_kib: actual 1407004.000 exceeds budget 1100000.000 + 15% tolerance (1265000.000)
- total_file_wall_seconds: actual 5332.068 exceeds budget 4000.000 + 15% tolerance (4600.000)
- causes.ace_page_enter: actual 556.202 exceeds budget 400.000 + 15% tolerance (460.000)
- causes.parser_create: actual 54.303 exceeds budget 35.000 + 15% tolerance (40.250)
- causes.pilot_pause_delay: actual 232.133 exceeds budget 190.000 + 15% tolerance (218.500)
- causes.subprocess_run: actual 614.409 exceeds budget 320.000 + 15% tolerance (368.000)
- causes.textual_app_run_test_enter: actual 478.373 exceeds budget 350.000 + 15% tolerance (402.500)
error: recipe `test-cost` failed on line 406 with exit code 1
error: recipe `check-full` failed on line 650 with exit code 1
```

## Your next action

You are resuming the landing of epic bead sase-ng.1 (Retire dead ACE in-process launch and cleanup bodies). Steps 1 and 2 of the landing are already DONE and recorded in full as the "LANDING VERIFICATION (sase-ng.1.land, HEAD c89e5bbeb)" note on sase-ng.1; read it with `sase bead show sase-ng.1` before acting. Do not redo that verification. The only thing that was outstanding is the combined-tree `just check-full` gate the epic plan requires before the close, which is the run you are being handed.

TRIAGE THE RESULT FIRST.
- Two gates are known-red on master and are NOT this epic's work. Do not file new task beads for them. tools/check_test_cost_budgets (peak_worker_rss_kib, causes.ace_page_enter, causes.parser_create, causes.textual_app_run_test_enter) is tracked on sase-j0 - phases sase-ng.1.5 and sase-ng.1.6 already recorded +1s there, so this reporter has already counted; add `sase bead note sase-j0` with this run's numbers instead of another +1. `just selection-health --fail-on-new-flake` overflow nodes are tracked on sase-jq, sase-jb, sase-kd and peers - triage each named node through your sase_new_task skill and corroborate rather than creating duplicates.
- Any lint/fmt/mypy/symvision failure, or any pytest failure, is a real blocker. Reproduce it, then decide whether this epic caused it by stashing or by checking whether the failing area touches the epic's surface (durable RUN_LAUNCH payloads, sase.agent.force_reuse_launch, src/sase/main/query_handler/_launch.py, ACE launch/cleanup proc submission, ops/commands/agent.py cleanup payload application). If this epic caused it, that is remaining epic work: use your sase_plan skill to plan just the remaining work and complete its validate/revalidate/propose loop, and do NOT close. If it is unrelated and pre-existing, record it per the bead policy and continue to the close.

IF THE RUN IS CLEAN (or fails only on the two known-red gates above), FINISH THE LANDING IN THIS ORDER.
1. `sase bead epic-symbols sase-ng.1` must still report no entries (it did at handoff, and the Justfile whitelist holds only sase-n4.5/sase-n4/sase-p1.2 lines).
2. Close the epic: `sase bead close sase-ng.1 --note "<note>"`. The note must state what was verified in landing steps 1 and 2 - summarize the LANDING VERIFICATION note on the bead (deleted module inventory confirmed absent, zero proc_callable in src with only the preserved _submit_session_worker seam left in tests, force-reuse/warning-toast/cleanup-recovery wiring confirmed end to end, all child PROPOSED FOLLOW-UPs resolved with sase-p6 and sase-p7 filed ready and the sase-oc/sase-j0/force-reuse-assertion proposals resolved without new beads, the epic's own DISCOVERED ISSUE note confirmed stale because 65b72d43a already removed all six sase-ng.1.5 entries, and the nine non-epic commits since 97f5b6f03 reviewed with Justfile-only overlap and no doc or code owed) - and add this check-full run's outcome.
3. `just symvision` to confirm the whitelist is clean.
4. Set `status: done` in the frontmatter of /home/bryan/.sase/plans/202608/retire_dead_ace_launch_cleanup_bodies.md (the epic's PLAN path).
5. PARENT HANDLING. sase-ng.1's parent is sase-ng, which is a TASK bead (not a phase and not a plan bead), currently in_progress, sized large, and its description asks for exactly the work this epic delivered: retire both dead in-process body families and both proc_callable parameters and migrate the affected test doubles onto the durable submit paths. Confirm that against the closed epic, then close it normally with `sase bead close sase-ng --note "<what you verified>"`, noting that sase-p6 and sase-p7 carry the two capabilities the plan deliberately scoped out. sase-ng has no parent above it, so stop there. If anything about sase-ng looks incomplete or ambiguous, do not force it: leave it open, put a note on it describing the blocker, and say so in your final response.

Never use --force on any close here. Report the check-full outcome, the closes you made, and anything you left open.
%xprompts_enabled:true

## Response

The check-full run came back with all lint gates and the full suite green; only the cost-budget gate failed, plus a flake-baseline gate I ran separately that names two of this epic's own test nodes. Let me triage the unrelated node through the proper skill first.

Landing complete. Both beads are closed.

## check-full outcome (monitor 7jzhrte86141, 23m3s at master c89e5bbeb)

Every lint gate green (fmt, keep-sorted, ruff, mypy, flags, pyscripts, test-waits, changelog, terminology, symvision, toobig), SASE + committed-plan validation green, full suite **32563 passed / 13 skipped / 0 failed**. The only failure was `tools/check_test_cost_budgets` — the standing master-red gate on **sase-j0**. I recorded the numbers there as a note (not another +1; sase-ng.1.5/1.6 already counted), including a finding worth a human look: this run missed 9 budget keys where two earlier runs on the same tree missed the usual 4. Re-checking all three recordings against the committed budgets isolates the extra 5 to host load (12 workers/1076s vs 14 workers/672–754s) — they're wall-derived keys plus per-worker collection CPU, so they'll keep flapping unless measured per-worker or at a fixed worker count.

## One real finding, and it was this epic's

`test-cost` aborts check-full before its last gate, so I ran `just selection-health --fail-on-new-flake` separately. It named three nodes — **two of them this epic's own**: the `test_force_reuse_launch_seam.py` unauthorized-path nodes, which failed on trees 88a8400/97f5b6f03(×2)/6ac274be5 while the helper asserted `launch_agents_from_cwd(prompt, segment_extra_env=None)`, until 13e9ccbc9 dropped the over-specified keyword. I retired that evidence through the baseline file's documented mechanism — a `# fixed-at: 2026-08-17T20:21:41Z` block in `tests/reproducible_flake_baseline.txt` naming sase-ng.1.1 and 13e9ccbc9 (6 records retired; the gate now clears both nodes). Re-verified: 12 seam tests pass, 41 selection-health gate/retirement tests pass. The third node (`test_on_alias_edited_offers_commit_when_in_repo`) is sase-oh's pre-existing holdout, untouched by this epic — corroborated there with a +1 rather than a new bead, and sase-oh explicitly forbids baselining it.

## Closes

- `sase bead epic-symbols sase-ng.1` → no entries. **sase-ng.1 closed** with a note covering verify + integrate + this run.
- Plan file `202608/retire_dead_ace_launch_cleanup_bodies.md` → `status: done`.
- **sase-ng closed** (task, no parent above). Re-verified its ask fresh: both body families gone from src/tests/docs, zero `proc_callable` in `src/`, neither `_submit_launch_proc` nor `_submit_cleanup_proc` takes one, and the six remaining test mentions are positional stand-ins for `_submit_session_worker`'s `body` — a different live seam. Noted that sase-p6/sase-p7 carry the two deliberately scoped-out capabilities.

## Left open (none of it this epic's)

- **`just symvision` is not clean** — six `sase-p1.2(...)` glossary entries went stale when that phase closed at 23:19:10Z, mid-landing. None are sase-ng.1's. Recorded as a DISCOVERED ISSUE on the in-progress epic **sase-p1**; sase-p1.6 is still open and is likely the bead they should be re-keyed to, but those symbols and that judgment belong to sase-p1, so I did not touch its Justfile lines.
- sase-j0 (cost gate), sase-oh (flake holdout), sase-p6/sase-p7 (ready tasks).

One uncommitted change is in the tree: `tests/reproducible_flake_baseline.txt` (the fixed-at block). I did not commit it — say the word and I'll run it through `/sase_git_commit`.

Close published cleanly — no unpublished-close diagnostic. Now committing the baseline change.

Done — the finalizer's requirement is satisfied and the tree is clean.

## What I did

**Verified the close is published.** Re-ran `sase bead close sase-ng.1` with the full verification note. It reported `Already closed sase-ng.1 … (2026-08-17T23:51:03Z · done)` and recorded the note — no `committed locally but NOT published` diagnostic, so the close reached the shared store, not just this checkout.

**Committed the one dirty file.** `tests/reproducible_flake_baseline.txt` was mine: the `# fixed-at:` block retiring the two `test_force_reuse_launch_seam.py` nodes whose flake evidence all predates 13e9ccbc9. Landed as `f77d940d6` (`test(flake-baseline): retire pre-fix force-reuse seam evidence`) through `/sase_git_commit`; it rebased onto two upstream commits that arrived meanwhile. `git status --short --branch` now shows `master...origin/master` with no ahead/behind and nothing dirty.

One warning from the commit: prompt-archive publication was deferred because the agents sync lock was busy, on top of 22 pre-existing quarantined agent-hood requests. I ran the remediation it named (`sase agent sync --retry-quarantined`), which exited 0 silently.

## Landing state (unchanged from the prior pass)

- **sase-ng.1** closed; plan file `202608/retire_dead_ace_launch_cleanup_bodies.md` marked `status: done`.
- **sase-ng** closed (task, no parent above it).
- check-full: all lint gates green, **32563 passed / 13 skipped / 0 failed**; only the standing master-red `tools/check_test_cost_budgets` gate failed, recorded on sase-j0.

## Still open, none of it this epic's

- **`just symvision` is not clean** — six stale `sase-p1.2(...)` glossary whitelist entries, orphaned when that phase closed mid-landing. Recorded as a DISCOVERED ISSUE on the in-progress epic **sase-p1**; sase-p1.6 is the likely re-key target, but that judgment is sase-p1's to make.
- sase-j0 (cost-budget gate), sase-oh (flake holdout it forbids baselining), sase-p6 / sase-p7 (ready tasks carrying the two capabilities this plan deliberately scoped out).
