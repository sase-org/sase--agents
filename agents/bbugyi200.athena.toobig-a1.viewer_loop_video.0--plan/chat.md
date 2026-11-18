# Chat History - ace-run (toobig-a1.viewer_loop_video.0--plan)

- **TIMESTAMP:** 2026-11-17 21:59:52 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-a1.viewer_loop_video.0--plan

# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: v6pr4ccsm8sg
Inspect with: sase monitor show v6pr4ccsm8sg
Monitor turn: toobig-a1.viewer_loop_video.0--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11

Command:

```sh
sase tool run check
```

Reason:

finish check for video viewer split

Next action:

Check the joined sase tool run check result with sase tool show; fix any NEW failures in the split files or retargeted tests, then reply to the user.


## Prompt

%id:toobig-a1.viewer_loop_video.0
%clan(toobig-a1, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 5 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 915  src/sase/ace/tui/graphics/_viewer_video_frames.py[/bold #FFAF5F]
[bold #FFAF5F]◆ 900  src/sase/ace/tui/graphics/_viewer_loop_video.py[/bold #FFAF5F]
[#87D7FF]• 738  tests/ace/tui/test_leader_keymap_dispatch.py[/#87D7FF]
[#87D7FF]• 719  src/sase/macro/workflow_runner.py[/#87D7FF]
[#87D7FF]• 704  tests/ace/tui/test_artifacts_beads_filtering.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/ace/tui/graphics/_viewer_loop_video.py` file into multiple files? Use your best
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

Split complete. `src/sase/ace/tui/graphics/_viewer_loop_video.py` (900 lines) is now a 13-line facade re-exporting only `run_video_inspect`, with three new modules:

- [`_viewer_loop_video_common.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/graphics/_viewer_loop_video_common.py) (297 lines): shared key/timestamp/layout helpers with public cross-module names.
- [`_viewer_loop_video_session.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/graphics/_viewer_loop_video_session.py) (239 lines): `VideoInspectSessionBase` plus `VideoInspectOutcome`.
- [`_viewer_loop_video_view.py`](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/graphics/_viewer_loop_video_view.py) (446 lines): rendering, key handling, `run_video_inspect`.

No `_`-prefixed imports cross the new modules. Tests were retargeted to the new public/private paths.

Verification: `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` all pass individually; the 67 video viewer tests pass; `just fmt` applied. `sase tool run check` (run `4601e39cd3f25c5f0c5de8427c8c5b73`) was still running past the sync ceiling, so I joined it to monitor `v6pr4c` — the follow-up will report its result.
