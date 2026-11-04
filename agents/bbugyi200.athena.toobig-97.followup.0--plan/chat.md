# Chat History - ace-run (toobig-97.followup.0--plan)

- **TIMESTAMP:** 2026-11-03 19:48:57 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-97.followup.0--plan

# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: m2kash98f0v0
Inspect with: sase monitor show m2kash98f0v0
Monitor turn: toobig-97.followup.0--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13

Command:

```sh
sase tool run check
```

Reason:

finish check (joined run)

Next action:

Read the check result with sase tool show a53843233ee1820814cac30634aab7b2 -l. If check passed, reply to the user summarizing the followup.py split. If it reported NEW failures in files the split touched, fix them (re-run just _lint-symvision, just _lint-mypy, just _lint-toobig as needed), then reply.


## Prompt

%id:toobig-97.followup.0
%clan(toobig-97, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 708  src/sase/turns/followup.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/turns/followup.py` file into multiple files? Use your best
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

## Response

The split is staged and verification is handed off — no final declaration was required.

Done so far: `src/sase/turns/followup.py` (708 lines) is now a 51-line facade re-exporting its original public API, with the implementation moved to [followup_launch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/turns/followup_launch.py) (402 lines), [followup_records.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/turns/followup_records.py) (151), [followup_starter.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/turns/followup_starter.py) (164), and [_followup_common.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/turns/_followup_common.py) (32, holds the shared `FollowupLaunchResult`). No `_`-prefixed name is imported across the new modules. Test monkeypatch targets for moved privates were retargeted (`followup_launch`, `followup_starter`), and the terminology allowlist gained the starter module.

`just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` all pass; a ruff-format fix for the retargeted tests was applied. `sase tool run check` (run `a53843233ee1820814cac30634aab7b2`) outlasted the sync ceiling during its test stage, so it was joined to monitor `m2kash98f0v0` with a verify follow-up that will read the result, fix any NEW failures in the touched files, and report.The split of `src/sase/turns/followup.py` is complete, lint-clean, and its full `sase tool run check` is still running under joined run `a53843233ee1820814cac30634aab7b2`, watched by staged monitor `m2kash` whose follow-up will handle the terminal result.

## What was done

**Split (all files ≤ 500 lines; verified with `wc -l`)**

- [followup.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/turns/followup.py) (51 lines) — facade preserving the original public import path and `__all__` (all 16 public names, plus `UpdateMetaFieldFn` re-exported for compatibility). Re-exports only public names, never `_`-prefixed ones.
- [followup_launch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/turns/followup_launch.py) (402 lines) — `TurnFollowupWorkspace`, `launch_turn_followup`, `vcs_ref_from_meta`, and the launch-only privates (`_vcs_ref_from_prompt`, `_resolve_turn_followup_vcs_ref`, `_strict_workspace_pair_error`, `_launch_vcs_followup_in_pool_workspace`, `_workspace_is_claimed`, `_workspace_dir_for_num`, `_POOL_FOLLOWUP_CLAIM_WORKFLOW`).
- [followup_records.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/turns/followup_records.py) (151 lines) — `FollowupPersistence`, `UpdateMetaFieldFn`, `spawn_turn_agent_session_successor`, `record_followup_launched`, `record_followup_not_launchable`, `persist_followup_prompt`.
- [followup_starter.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/turns/followup_starter.py) (164 lines) — both settle-timeout constants, `fork_target_for_settled_starter`, `starter_identity`, `wait_for_starter`, `wait_for_starter_artifacts_dir`, `wait_for_followup_started`, and the wait-only privates.
- [_followup_common.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/turns/_followup_common.py) (32 lines) — already-private module holding the one helper needed by two new modules, `FollowupLaunchResult`, under its public name. No `_`-prefixed name is imported across the new modules.

**Test retargeting (private monkeypatch targets moved with the code)**

- `tests/turns/test_followup_vcs_preallocation.py` — `_resolve_turn_followup_vcs_ref` / `_vcs_ref_from_prompt` now imported from `sase.turns.followup_launch`; patch targets moved to `sase.turns.followup_launch._workspace_dir_for_num`, `._workspace_is_claimed`, `.claim_next_axe_workspace_dir`.
- `tests/turns/test_followup_strict.py` — patch targets moved to `sase.turns.followup_launch.*`.
- `tests/turns/test_turns_substrate.py` — `_pid_is_running` patches moved to `sase.turns.followup_starter.*`.
- `tests/monitor/test_monitor_followup_workspace.py` — `shells_followup_module` alias now points at `sase.turns.followup_launch`.
- `tests/test_agent_session_terminology.py` — allowlist gained `src/sase/turns/followup_starter.py` (it now owns the legacy `agent_family`-key reader).
- Public-name patches (`DEFAULT_STARTER_SETTLE_TIMEOUT_SECONDS`, `STARTER_SETTLE_POLL_SECONDS`, `wait_for_starter_artifacts_dir` via the facade) were left untouched — the facade still serves them and lazy importers resolve through it.

## Verification results

- `just _lint-symvision` — pass ("All public/private classes/functions are used properly!").
- `just _lint-mypy` — pass ("Success: no issues found in 6368 source files").
- `just _lint-toobig` — pass (all files within limits).
- One `fmt (python)` failure from the retargeted test lines was fixed with ruff format.
- `sase tool run check` (run `a53843233ee1820814cac30634aab7b2`) — all stages through `committed plans` passed; it is now in its final `test (scoped)` stage. It outlasted the 10-minute sync ceiling, so per the tool's own escalation it was joined to staged monitor `m2kash` (`-p verify`), whose follow-up is instructed to read the result with `sase tool show`, fix any NEW failures in the touched follow-up files (re-running the three lints as needed), and report. Inline waiting is refused while the monitor holds the join, so this turn ends here and the monitor follow-up completes the deliverable.Done. The `src/sase/turns/followup.py` split is complete, all required lints pass, and the one NEW failure from the full check run is fixed and verified.

## Split (every file ≤ 500 lines)

`followup.py` (708 lines) is now a 51-line facade preserving the original public import path and `__all__` (all 16 public names, plus `UpdateMetaFieldFn` re-exported for compatibility). It re-exports only public names, never `_`-private ones:

- [followup_launch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/turns/followup_launch.py) (402) — `TurnFollowupWorkspace`, `launch_turn_followup`, `vcs_ref_from_meta`, plus the launch-only privates (`_vcs_ref_from_prompt`, `_resolve_turn_followup_vcs_ref`, `_strict_workspace_pair_error`, `_launch_vcs_followup_in_pool_workspace`, `_workspace_is_claimed`, `_workspace_dir_for_num`).
- [followup_records.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/turns/followup_records.py) (151) — `FollowupPersistence`, `UpdateMetaFieldFn`, `spawn_turn_agent_session_successor`, `record_followup_launched`, `record_followup_not_launchable`, `persist_followup_prompt`.
- [followup_starter.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/turns/followup_starter.py) (164) — both settle-timeout constants, `fork_target_for_settled_starter`, `starter_identity`, `wait_for_starter`, `wait_for_starter_artifacts_dir`, `wait_for_followup_started`, plus the wait-only privates.
- [_followup_common.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/turns/_followup_common.py) (32) — the already-private module holding the one helper needed by two new modules, `FollowupLaunchResult`, under its public name. No `_`-prefixed name is imported across the new modules.

## Test retargeting

Private monkeypatch targets moved with the code: `test_followup_vcs_preallocation.py` and `test_followup_strict.py` now patch `sase.turns.followup_launch.*`; `test_turns_substrate.py` patches `sase.turns.followup_starter._pid_is_running`; `test_monitor_followup_workspace.py` imports `followup_launch` as its patch module; the terminology allowlist gained `followup_starter.py`. Public-name patches on the facade (settle constants, `wait_for_starter_artifacts_dir` for lazy importers) were left as-is.

## Check result and the one NEW failure

`sase tool run check` (run `a53843233ee1820814cac30634aab7b2`, 21m29s, exit 1) passed every lint stage; its single NEW item was `tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_agent_session_retains_one_claim...`, which patches the facade's `wait_for_starter_artifacts_dir` to observe the production starter-settlement wait. That interception broke because `wait_for_starter` now resolves the name inside `followup_starter`, not the facade — the observer was never called (`observed == {}`). Per the keep-or-retarget rule I retargeted that test to patch `sase.turns.followup_starter` (one-line change; it owns both the function and the constant the test reads).

## Verification after the fix

- `just _lint-symvision` — pass; `just _lint-mypy` — pass (6368 files); `just _lint-toobig` — pass; ruff format/check clean on the edited test.
- Previously-failing e2e test: **passed** (5.71s).
- Neighboring suites: 37 passed (`test_followup_vcs_preallocation`, `test_followup_strict`, `test_turns_substrate`, terminology), 15 passed (monitor followup workspace, starter race, monitor result), 6 passed (full `test_monitor_capacity_e2e.py` file).

No re-run of the full 21-minute check was needed: the only NEW failure is fixed at its root cause and proven green along with every test file the split touched.
