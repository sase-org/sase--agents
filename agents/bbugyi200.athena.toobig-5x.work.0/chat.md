# Chat History - ace-run (toobig-5x.work.0)

- **TIMESTAMP:** 2026-09-23 08:34:01 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-5x.work.0

## Prompt

%id(work.0, clan=toobig-5x)
%model:@medium
%auto
%queue(capacity=3)
#gh:gh_sase-org__sase Can you help me split the `src/sase/bead/work.py` file up into multiple files? Use your best
%wait:toobig-5x.launch_cwd_agents.0
judgement, but let's aim to keep all files <=500 lines of code.

## Response

Done. `src/sase/bead/work.py` (710 lines) is now five files, all under 500 lines:

- [work_types.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/bead/work_types.py) (58 lines) – env/clan constants, `VCSLaunchContext`, `PatchLaunchContext`, `EpicPlanError`
- [work_plan.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/bead/work_plan.py) (256 lines) – `EpicWorkPlan`, wave-plan builder, Rust payload conversion
- [work_prompt.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/bead/work_prompt.py) (405 lines) – model directives, `render_multi_prompt`, `render_task_prompt`, clan/capacity/VCS helpers
- [work_env.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/bead/work_env.py) (99 lines) – epic/task launch-environment metadata
- [work.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25/src/sase/bead/work.py) (62 lines) – thin facade re-exporting the public surface, so existing non-test imports are untouched

Private helpers (`_PhaseAssignment`, `_CycleError`, `_build_epic_work_plan`, …) moved to their canonical homes since the repo's symvision gate forbids cross-file private imports. Seven test files were updated to import those from `sase.bead.work_plan` / patch `sase.bead.work_prompt.get_big_epic_phase_threshold` directly; all other callers keep using `sase.bead.work`.

Verification observed: 230 tests passed across all work-consumer suites (116 + 114), `just fmt` clean, symvision reports zero violations in the new files.

One finding: `just check` still fails on a pre-existing symvision error (`ExpandedLaunchSegments` in `src/sase/agent/launch_cwd_segments.py`) that I confirmed exists on the untouched baseline too. I left it alone as out of scope.
