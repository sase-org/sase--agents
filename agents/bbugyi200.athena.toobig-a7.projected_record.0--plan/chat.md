# Chat History - ace-run (toobig-a7.projected_record.0--plan)

- **TIMESTAMP:** 2026-11-19 05:16:12 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-a7.projected_record.0--plan

# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: a77awzsc18jp
Inspect with: sase monitor show a77awzsc18jp
Monitor turn: toobig-a7.projected_record.0--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21

Command:

```sh
sase tool run check
```

Reason:

finish check (joined run)

Next action:

Read the check run result with sase tool show 2f8213a252bc37cb94676eae4b7e8151 -l, fix any NEW failures in the split files (src/sase/ace/tui/models/_projected_record*.py and retargeted tests), re-verify with sase tool run check if you change code, then reply to the user with the split summary and verification outcome.


## Prompt

%id:toobig-a7.projected_record.0
%clan(toobig-a7, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 765  tests/test_agents_tab_delta_copy_fast_path.py[/#87D7FF]
[#87D7FF]• 712  src/sase/ace/tui/models/_projected_record.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/models/_projected_record.py` file into multiple files? Use your best
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

Split the 712-line module into four files, all under 500 lines. The original import path is preserved through a facade that only re-exports public names, and no new module imports a `_`-prefixed name.

New layout in `src/sase/ace/tui/models/`:

- [facade](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/ace/tui/models/_projected_record.py) (33 lines): re-exports the 11 public names and keeps the original `__all__` plus the four previously importable-but-unlisted names (`apply_projected_agent_record`, `load_projected_agent_record`, `prepare_projected_agent_copy`, `projected_agent_compact_copy_value`).
- [detail owner](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/ace/tui/models/_projected_record_detail.py) (216 lines): hydration gating, marks, compact-copy helpers, bounded owner, plus two renamed shared helpers with public names (`stash_applied_detail`, `note_projected_detail_retained`); `_detail_owner`, `_release_projected_agent_detail`, and the attr constants stay private in-file.
- [load/hydrate](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/ace/tui/models/_projected_record_load.py) (96 lines): `resolve_step_output`, `resolve_linked_repos`, `load_projected_agent_record`, `hydrate_projected_agent`; imports only public names from detail and restore.
- [restore](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/ace/tui/models/_projected_record_restore.py) (421 lines): `apply_projected_agent_record` plus the full-record, meta/row, done-turn, and step-output helpers, all private in-file except the one public apply entry.

Retargeted tests and census to the canonical locations (facade imports still exercise the public path): `test_projected_record.py`, `_test_projected_detail_retention_owner.py`, `_test_projected_detail_retention_worker.py`, `test_agent_compact_list_integration.py`, `test_agent_compact_workflow_loaders.py`, plus [census source](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/src/sase/ace/tui/util/_gc_policy_census.py) and its test now probe `sase.ace.tui.models._projected_record_detail._detail_owner`.

Verification observed: `just _lint-symvision` passes ("All public/private classes/functions are used properly!"), `just _lint-mypy` passes (no issues in 6627 + 103 files), `just _lint-toobig` passes (src within 700 info limit). Ran `just fix` before verification. `sase tool run check` (run `2f8213a252bc37cb94676eae4b7e8151`) was still running after 8m30s and escalated with exit 124; joined it with `sase monitor start -J 2f8213a252bc37cb94676eae4b7e8151 -p verify`, staged as monitor `a77awz`. The follow-up will read that run, fix any new failures in the split, and report.
