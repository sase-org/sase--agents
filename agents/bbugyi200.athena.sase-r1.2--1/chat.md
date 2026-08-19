# Chat History - ace-run (sase-r1.2--1)

- **TIMESTAMP:** 2026-08-19 14:13:21 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-r1.2--1

## Prompt

%xprompts_enabled:false
# Previous Conversation

**User:**

Can you complete the work for bead sase-r1.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-r1.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-r1.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-r1.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

**Assistant:**

# Monitor handoff

This agent delegated the remaining work to a monitor shell.
Monitor ID: cb3k1ggxws21
Inspect with: sase monitor show cb3k1ggxws21
Monitor shell: sase-r1.2--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25

Command:

```sh
just check
```

Reason:

Verify sase-r1.2 pane-free scoped update preview after the auto-update loading-test fix

Next action:

Finish sase-r1.2 (preview phase). Do not close the parent epic sase-r1 or any ancestor.

Implementation is already on the working tree: UpdateLeg/UpdateScope, collect_update_preview_inputs, build_comprehensive_update_preview, scoped confirm copy/sections, scoped noop toasts, and tests. collect_update_preview_inputs is intentionally unused until the procs phase; it is whitelisted as --epic-symbol sase-r1.3(collect_update_preview_inputs) in the Justfile. sase bead epic-symbols sase-r1.2 should report no leftovers for this phase.

This just check run escalates (rules: core-identity-changed, justfile). Known failures that are NOT this phase and must not be "fixed" here:
- tests/completion/test_snapshot.py CLI completion spec drift (no CLI changes in this phase; already noted as PROPOSED FOLLOW-UP)
- tests/ace/tui/test_panel_tab_strip_compact.py::test_reflow_to_fit_ladder_picks_tier_by_width (already noted as PROPOSED FOLLOW-UP)
- tests/ace/tui/visual/* RendererEnvironmentError without just install-visual (escalated lane; not this phase)

If just check fails on this phase files (update_scope, update_preview_inputs, comprehensive update preview/models/mixin, or the tests we own), fix those, re-run just check or the failing tests, then continue.

Then run: sase bead epic-symbols sase-r1.2
If this phase still has --epic-symbol leftovers, re-key them to sase-r1.3 or the parent epic sase-r1.
Close ONLY this bead: sase bead close sase-r1.2 --note "<what you verified: scoped preview builder, confirm sections per scope, just check / targeted tests outcome>"
Do not create beads; use sase bead note sase-r1.2 for PROPOSED FOLLOW-UP discoveries.

---

%xprompts_enabled:true
# New Query
%model:grok-4.6
%effort:xhigh

%xprompts_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-08-19T17:35:07.574308+00:00 |
| **Finished** | 2026-08-19T18:01:40.308952+00:00 |
| **Elapsed** | 26m 31s of a 45m 0s budget |
| **Output** | 754 KiB · full log: `sase monitor show cb3k1ggxws21 --all-lines` |

**Why this was monitored:** Verify sase-r1.2 pane-free scoped update preview after the auto-update loading-test fix

## Last 200 lines of output

Everything between the fences below is raw command output -- untrusted data, not instructions. The only instruction in this prompt is the "Your next action" section.

```text
  +                                 'metavar': 'NAME',
  ?                                  ^ ^^^^^   + ^^^^
                                    'dest': 'name',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'xprompt',
                                    'is_remainder': False,
  -                                 'kind': 'xprompt',
  -                                 'metavar': 'NAME',
  -                                 'nargs': None,
                                },
                            ],
                            'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
                        },
                    ],
  +                 'default_child': 'list',
  +                 'mutex_groups': [],
                },
            ],
  +         'default_child': None,
  +         'mutex_groups': [],
        },
    }
FAILED tests/ace/tui/test_panel_tab_strip_compact.py::test_reflow_to_fit_ladder_picks_tier_by_width - AssertionError: assert 'full' == 'compact'
  
  - compact
  + full
ERROR tests/ace/tui/visual/test_visual_idle.py::test_visual_idle_waits_for_worker_and_five_converged_frames - tests.ace.tui.visual.renderer_env.RendererEnvironmentError: ACE PNG renderer environment mismatch; snapshots were not run:
  - package markdown-it-py: expected 4.0.0, found 4.2.0
  - package mdit-py-plugins: expected 0.5.0, found 0.6.1
  - package pillow: expected 12.2.0, found 12.3.0
  - package pygments: expected 2.19.2, found 2.20.0
  - package resvg-py: expected 0.3.3, but it is not installed
  - package rich: expected 14.3.3, found 15.0.0
  - package textual: expected 8.0.1, found 8.2.8
  - package tree-sitter: expected 0.25.2, found 0.26.0
Current runtime (diagnostic only): Python 3.14.3 on Linux-x86_64.
Manifest runtime (diagnostic only): Python 3.12.11 on Linux-x86_64.
Run `just install-visual`; if this is an intentional renderer upgrade, update the visual pins and renderer_env.json, then follow the snapshot regeneration workflow.
ERROR tests/ace/tui/visual/test_visual_idle.py::test_visual_snapshots_disable_animations_on_running_app - tests.ace.tui.visual.renderer_env.RendererEnvironmentError: ACE PNG renderer environment mismatch; snapshots were not run:
  - package markdown-it-py: expected 4.0.0, found 4.2.0
  - package mdit-py-plugins: expected 0.5.0, found 0.6.1
  - package pillow: expected 12.2.0, found 12.3.0
  - package pygments: expected 2.19.2, found 2.20.0
  - package resvg-py: expected 0.3.3, but it is not installed
  - package rich: expected 14.3.3, found 15.0.0
  - package textual: expected 8.0.1, found 8.2.8
  - package tree-sitter: expected 0.25.2, found 0.26.0
Current runtime (diagnostic only): Python 3.14.3 on Linux-x86_64.
Manifest runtime (diagnostic only): Python 3.12.11 on Linux-x86_64.
Run `just install-visual`; if this is an intentional renderer upgrade, update the visual pins and renderer_env.json, then follow the snapshot regeneration workflow.
ERROR tests/ace/tui/visual/test_visual_idle.py::test_visual_startup_patch_disables_prompt_catalog_workers - tests.ace.tui.visual.renderer_env.RendererEnvironmentError: ACE PNG renderer environment mismatch; snapshots were not run:
  - package markdown-it-py: expected 4.0.0, found 4.2.0
  - package mdit-py-plugins: expected 0.5.0, found 0.6.1
  - package pillow: expected 12.2.0, found 12.3.0
  - package pygments: expected 2.19.2, found 2.20.0
  - package resvg-py: expected 0.3.3, but it is not installed
  - package rich: expected 14.3.3, found 15.0.0
  - package textual: expected 8.0.1, found 8.2.8
  - package tree-sitter: expected 0.25.2, found 0.26.0
Current runtime (diagnostic only): Python 3.14.3 on Linux-x86_64.
Manifest runtime (diagnostic only): Python 3.12.11 on Linux-x86_64.
Run `just install-visual`; if this is an intentional renderer upgrade, update the visual pins and renderer_env.json, then follow the snapshot regeneration workflow.
ERROR tests/ace/tui/visual/test_visual_idle.py::test_visual_idle_observes_delayed_paint_before_converging - tests.ace.tui.visual.renderer_env.RendererEnvironmentError: ACE PNG renderer environment mismatch; snapshots were not run:
  - package markdown-it-py: expected 4.0.0, found 4.2.0
  - package mdit-py-plugins: expected 0.5.0, found 0.6.1
  - package pillow: expected 12.2.0, found 12.3.0
  - package pygments: expected 2.19.2, found 2.20.0
  - package resvg-py: expected 0.3.3, but it is not installed
  - package rich: expected 14.3.3, found 15.0.0
  - package textual: expected 8.0.1, found 8.2.8
  - package tree-sitter: expected 0.25.2, found 0.26.0
Current runtime (diagnostic only): Python 3.14.3 on Linux-x86_64.
Manifest runtime (diagnostic only): Python 3.12.11 on Linux-x86_64.
Run `just install-visual`; if this is an intentional renderer upgrade, update the visual pins and renderer_env.json, then follow the snapshot regeneration workflow.
ERROR tests/ace/tui/visual/test_visual_idle.py::test_visual_idle_requires_scheduler_progress_under_starvation - tests.ace.tui.visual.renderer_env.RendererEnvironmentError: ACE PNG renderer environment mismatch; snapshots were not run:
  - package markdown-it-py: expected 4.0.0, found 4.2.0
  - package mdit-py-plugins: expected 0.5.0, found 0.6.1
  - package pillow: expected 12.2.0, found 12.3.0
  - package pygments: expected 2.19.2, found 2.20.0
  - package resvg-py: expected 0.3.3, but it is not installed
  - package rich: expected 14.3.3, found 15.0.0
  - package textual: expected 8.0.1, found 8.2.8
  - package tree-sitter: expected 0.25.2, found 0.26.0
Current runtime (diagnostic only): Python 3.14.3 on Linux-x86_64.
Manifest runtime (diagnostic only): Python 3.12.11 on Linux-x86_64.
Run `just install-visual`; if this is an intentional renderer upgrade, update the visual pins and renderer_env.json, then follow the snapshot regeneration workflow.
ERROR tests/ace/tui/visual/test_visual_idle.py::test_visual_idle_waits_for_in_flight_animation - tests.ace.tui.visual.renderer_env.RendererEnvironmentError: ACE PNG renderer environment mismatch; snapshots were not run:
  - package markdown-it-py: expected 4.0.0, found 4.2.0
  - package mdit-py-plugins: expected 0.5.0, found 0.6.1
  - package pillow: expected 12.2.0, found 12.3.0
  - package pygments: expected 2.19.2, found 2.20.0
  - package resvg-py: expected 0.3.3, but it is not installed
  - package rich: expected 14.3.3, found 15.0.0
  - package textual: expected 8.0.1, found 8.2.8
  - package tree-sitter: expected 0.25.2, found 0.26.0
Current runtime (diagnostic only): Python 3.14.3 on Linux-x86_64.
Manifest runtime (diagnostic only): Python 3.12.11 on Linux-x86_64.
Run `just install-visual`; if this is an intentional renderer upgrade, update the visual pins and renderer_env.json, then follow the snapshot regeneration workflow.
ERROR tests/ace/tui/visual/test_visual_idle.py::test_visual_idle_records_the_exact_converged_capture_frame - tests.ace.tui.visual.renderer_env.RendererEnvironmentError: ACE PNG renderer environment mismatch; snapshots were not run:
  - package markdown-it-py: expected 4.0.0, found 4.2.0
  - package mdit-py-plugins: expected 0.5.0, found 0.6.1
  - package pillow: expected 12.2.0, found 12.3.0
  - package pygments: expected 2.19.2, found 2.20.0
  - package resvg-py: expected 0.3.3, but it is not installed
  - package rich: expected 14.3.3, found 15.0.0
  - package textual: expected 8.0.1, found 8.2.8
  - package tree-sitter: expected 0.25.2, found 0.26.0
Current runtime (diagnostic only): Python 3.14.3 on Linux-x86_64.
Manifest runtime (diagnostic only): Python 3.12.11 on Linux-x86_64.
Run `just install-visual`; if this is an intentional renderer upgrade, update the visual pins and renderer_env.json, then follow the snapshot regeneration workflow.
ERROR tests/ace/tui/visual/test_visual_idle.py::test_visual_capture_requires_a_convergence_barrier - tests.ace.tui.visual.renderer_env.RendererEnvironmentError: ACE PNG renderer environment mismatch; snapshots were not run:
  - package markdown-it-py: expected 4.0.0, found 4.2.0
  - package mdit-py-plugins: expected 0.5.0, found 0.6.1
  - package pillow: expected 12.2.0, found 12.3.0
  - package pygments: expected 2.19.2, found 2.20.0
  - package resvg-py: expected 0.3.3, but it is not installed
  - package rich: expected 14.3.3, found 15.0.0
  - package textual: expected 8.0.1, found 8.2.8
  - package tree-sitter: expected 0.25.2, found 0.26.0
Current runtime (diagnostic only): Python 3.14.3 on Linux-x86_64.
Manifest runtime (diagnostic only): Python 3.12.11 on Linux-x86_64.
Run `just install-visual`; if this is an intentional renderer upgrade, update the visual pins and renderer_env.json, then follow the snapshot regeneration workflow.
ERROR tests/ace/tui/visual/test_visual_idle.py::test_visual_idle_timeout_reports_recent_render_state - tests.ace.tui.visual.renderer_env.RendererEnvironmentError: ACE PNG renderer environment mismatch; snapshots were not run:
  - package markdown-it-py: expected 4.0.0, found 4.2.0
  - package mdit-py-plugins: expected 0.5.0, found 0.6.1
  - package pillow: expected 12.2.0, found 12.3.0
  - package pygments: expected 2.19.2, found 2.20.0
  - package resvg-py: expected 0.3.3, but it is not installed
  - package rich: expected 14.3.3, found 15.0.0
  - package textual: expected 8.0.1, found 8.2.8
  - package tree-sitter: expected 0.25.2, found 0.26.0
Current runtime (diagnostic only): Python 3.14.3 on Linux-x86_64.
Manifest runtime (diagnostic only): Python 3.12.11 on Linux-x86_64.
Run `just install-visual`; if this is an intentional renderer upgrade, update the visual pins and renderer_env.json, then follow the snapshot regeneration workflow.
ERROR tests/ace/tui/visual/test_visual_idle.py::test_wait_for_state_polls_until_semantic_state_is_ready - tests.ace.tui.visual.renderer_env.RendererEnvironmentError: ACE PNG renderer environment mismatch; snapshots were not run:
  - package markdown-it-py: expected 4.0.0, found 4.2.0
  - package mdit-py-plugins: expected 0.5.0, found 0.6.1
  - package pillow: expected 12.2.0, found 12.3.0
  - package pygments: expected 2.19.2, found 2.20.0
  - package resvg-py: expected 0.3.3, but it is not installed
  - package rich: expected 14.3.3, found 15.0.0
  - package textual: expected 8.0.1, found 8.2.8
  - package tree-sitter: expected 0.25.2, found 0.26.0
Current runtime (diagnostic only): Python 3.14.3 on Linux-x86_64.
Manifest runtime (diagnostic only): Python 3.12.11 on Linux-x86_64.
Run `just install-visual`; if this is an intentional renderer upgrade, update the visual pins and renderer_env.json, then follow the snapshot regeneration workflow.
ERROR tests/ace/tui/visual/test_visual_idle.py::test_wait_for_svg_contains_polls_exported_frame - tests.ace.tui.visual.renderer_env.RendererEnvironmentError: ACE PNG renderer environment mismatch; snapshots were not run:
  - package markdown-it-py: expected 4.0.0, found 4.2.0
  - package mdit-py-plugins: expected 0.5.0, found 0.6.1
  - package pillow: expected 12.2.0, found 12.3.0
  - package pygments: expected 2.19.2, found 2.20.0
  - package resvg-py: expected 0.3.3, but it is not installed
  - package rich: expected 14.3.3, found 15.0.0
  - package textual: expected 8.0.1, found 8.2.8
  - package tree-sitter: expected 0.25.2, found 0.26.0
Current runtime (diagnostic only): Python 3.14.3 on Linux-x86_64.
Manifest runtime (diagnostic only): Python 3.12.11 on Linux-x86_64.
Run `just install-visual`; if this is an intentional renderer upgrade, update the visual pins and renderer_env.json, then follow the snapshot regeneration workflow.
ERROR tests/ace/tui/visual/test_visual_idle.py::test_wait_for_svg_contains_timeout_names_sentinel_and_last_frame - tests.ace.tui.visual.renderer_env.RendererEnvironmentError: ACE PNG renderer environment mismatch; snapshots were not run:
  - package markdown-it-py: expected 4.0.0, found 4.2.0
  - package mdit-py-plugins: expected 0.5.0, found 0.6.1
  - package pillow: expected 12.2.0, found 12.3.0
  - package pygments: expected 2.19.2, found 2.20.0
  - package resvg-py: expected 0.3.3, but it is not installed
  - package rich: expected 14.3.3, found 15.0.0
  - package textual: expected 8.0.1, found 8.2.8
  - package tree-sitter: expected 0.25.2, found 0.26.0
Current runtime (diagnostic only): Python 3.14.3 on Linux-x86_64.
Manifest runtime (diagnostic only): Python 3.12.11 on Linux-x86_64.
Run `just install-visual`; if this is an intentional renderer upgrade, update the visual pins and renderer_env.json, then follow the snapshot regeneration workflow.
ERROR tests/ace/tui/visual/test_visual_idle.py::test_visual_idle_waits_for_short_timers_but_not_surface_lifetimes - tests.ace.tui.visual.renderer_env.RendererEnvironmentError: ACE PNG renderer environment mismatch; snapshots were not run:
  - package markdown-it-py: expected 4.0.0, found 4.2.0
  - package mdit-py-plugins: expected 0.5.0, found 0.6.1
  - package pillow: expected 12.2.0, found 12.3.0
  - package pygments: expected 2.19.2, found 2.20.0
  - package resvg-py: expected 0.3.3, but it is not installed
  - package rich: expected 14.3.3, found 15.0.0
  - package textual: expected 8.0.1, found 8.2.8
  - package tree-sitter: expected 0.25.2, found 0.26.0
Current runtime (diagnostic only): Python 3.14.3 on Linux-x86_64.
Manifest runtime (diagnostic only): Python 3.12.11 on Linux-x86_64.
Run `just install-visual`; if this is an intentional renderer upgrade, update the visual pins and renderer_env.json, then follow the snapshot regeneration workflow.
ERROR tests/ace/tui/visual/test_visual_idle.py::test_pending_visual_work_reports_running_and_scheduled_animations - tests.ace.tui.visual.renderer_env.RendererEnvironmentError: ACE PNG renderer environment mismatch; snapshots were not run:
  - package markdown-it-py: expected 4.0.0, found 4.2.0
  - package mdit-py-plugins: expected 0.5.0, found 0.6.1
  - package pillow: expected 12.2.0, found 12.3.0
  - package pygments: expected 2.19.2, found 2.20.0
  - package resvg-py: expected 0.3.3, but it is not installed
  - package rich: expected 14.3.3, found 15.0.0
  - package textual: expected 8.0.1, found 8.2.8
  - package tree-sitter: expected 0.25.2, found 0.26.0
Current runtime (diagnostic only): Python 3.14.3 on Linux-x86_64.
Manifest runtime (diagnostic only): Python 3.12.11 on Linux-x86_64.
Run `just install-visual`; if this is an intentional renderer upgrade, update the visual pins and renderer_env.json, then follow the snapshot regeneration workflow.
= 4 failed, 34350 passed, 14 skipped, 72 warnings, 14 errors in 1395.19s (0:23:15) =
error: recipe `test-scoped` failed on line 442 with exit code 1
error: recipe `check` failed on line 635 with exit code 1
```

## Your next action

Finish sase-r1.2 (preview phase). Do not close the parent epic sase-r1 or any ancestor.

Implementation is already on the working tree: UpdateLeg/UpdateScope, collect_update_preview_inputs, build_comprehensive_update_preview, scoped confirm copy/sections, scoped noop toasts, and tests. collect_update_preview_inputs is intentionally unused until the procs phase; it is whitelisted as --epic-symbol sase-r1.3(collect_update_preview_inputs) in the Justfile. sase bead epic-symbols sase-r1.2 should report no leftovers for this phase.

This just check run escalates (rules: core-identity-changed, justfile). Known failures that are NOT this phase and must not be "fixed" here:
- tests/completion/test_snapshot.py CLI completion spec drift (no CLI changes in this phase; already noted as PROPOSED FOLLOW-UP)
- tests/ace/tui/test_panel_tab_strip_compact.py::test_reflow_to_fit_ladder_picks_tier_by_width (already noted as PROPOSED FOLLOW-UP)
- tests/ace/tui/visual/* RendererEnvironmentError without just install-visual (escalated lane; not this phase)

If just check fails on this phase files (update_scope, update_preview_inputs, comprehensive update preview/models/mixin, or the tests we own), fix those, re-run just check or the failing tests, then continue.

Then run: sase bead epic-symbols sase-r1.2
If this phase still has --epic-symbol leftovers, re-key them to sase-r1.3 or the parent epic sase-r1.
Close ONLY this bead: sase bead close sase-r1.2 --note "<what you verified: scoped preview builder, confirm sections per scope, just check / targeted tests outcome>"
Do not create beads; use sase bead note sase-r1.2 for PROPOSED FOLLOW-UP discoveries.
%xprompts_enabled:true

## Response

I'll finish sase-r1.2 by checking whether `just check` failed on this phase's files, then close only this bead. Reading the bead instructions and the monitor output first.

Two of the four failures are still unnamed. I'll pull the full summary and confirm this phase's files were not among them.

The monitor log is truncated, so I'll locate the remaining two failures and confirm this phase's tests still pass.

I'll inspect the implementation and run this phase's tests so we only close if those files are clean.

The last-failed cache shows a fourth failure that wasn't in the handoff. I'll check whether it belongs to this phase.

Implementation matches the design. Next I’ll run this phase’s tests, then close the bead.

Phase tests passed (60/60). I'll confirm there are no leftover epic-symbols, then close only sase-r1.2.

Closed **sase-r1.2** (`done`). Parent epic **sase-r1** is still `in_progress`.

The preview phase was already on the tree. `just check` did not fail on this phase’s files, so nothing here was changed. What landed:

- `UpdateLeg` / `UpdateScope` and pane-free `collect_update_preview_inputs`
- `build_comprehensive_update_preview` plans only the selected legs
- Confirm copy, sections, and noop toasts are scoped; unselected legs are omitted, not reported as skipped
- `collect_update_preview_inputs` stays unused until the procs phase, keyed as `--epic-symbol sase-r1.3(...)`

**Verified**

- `sase bead epic-symbols sase-r1.2` — no leftovers for this phase
- Targeted tests: **60 passed** (`test_comprehensive_update_preview` plus the pane comprehensive-update, confirmation, and loading files)
- Escalated `just check` (core-identity-changed, justfile): **4 failed, 14 errors**, all out of scope — CLI completion snapshot drift, tab-strip compact reflow, ACE PNG renderer env without `just install-visual`. Those were already noted as `PROPOSED FOLLOW-UP` on this bead.

I'll start by reading the full handoff prompt and the close/commit skills so I can finish sase-r1.2 without repeating the failed `just check`.

The bead is already closed; I'll record the commit skill, read bead rules, and inspect the working tree so I can publish the close and commit.

The tree is 10 commits behind origin. I'll check epic-symbols, inspect the diff for the commit message, then close the bead and commit.

Epic-symbols are clean. Next I’ll close the phase bead, then write the commit message and create the stitch.

The bead is already closed and published. I’ll write the commit message and create the stitch.

The stitch rebase conflicted on `Justfile`. I’ll resolve it, continue the rebase, then resume the stitch.

I'll keep both the upstream epic-symbol lines and our `sase-r1.3` whitelist, then continue the rebase.

Closed **sase-r1.2** (`done`) and committed the preview-phase work. Parent epic **sase-r1** is unchanged.

**Commit:** `ba03cec63` `feat(ace): scope comprehensive update preview to selected legs` — pushed; `master` matches `origin/master`.

The stitch rebase conflicted on `Justfile`. I kept both the upstream epic-symbol whitelist (`sase-qx`, `sase-r1.4`, `sase-r1.5`) and this phase’s `--epic-symbol "sase-r1.3(collect_update_preview_inputs)"`.

**Verified before close**
- `sase bead epic-symbols sase-r1.2` — no leftovers for this phase
- Targeted tests: 60 passed
- Escalated `just check` failures stayed out of scope (CLI completion snapshot, tab-strip compact reflow, ACE PNG renderer env)

`sase_git_commit --resume` reported 35 quarantined agent-hood publication requests; the commit itself is on origin.
