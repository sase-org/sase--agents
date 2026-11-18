# Chat History - ace-run (toobig-a2.test_video_inspect.0)

- **TIMESTAMP:** 2026-11-18 10:09:12 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-a2.test_video_inspect.0

## Prompt

%auto
%id(test_video_inspect.0, clan=toobig-a2)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/ace/tui/artifact_file_viewer/test_video_inspect.py` file into multiple files? Use your best
%wait:toobig-a2.chop_typed_admission.0
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

Done. The 840-line [test_video_inspect.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/ace/tui/artifact_file_viewer/test_video_inspect.py) is now a 77-line facade over three focused modules, each under 500 lines.

New layout in `tests/ace/tui/artifact_file_viewer/`:

- [test_video_inspect_keys.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/ace/tui/artifact_file_viewer/test_video_inspect_keys.py) (126 lines) — key decoding/assembly/reading, timestamp math, status bar, storyboard layout.
- [test_video_inspect_loop.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/ace/tui/artifact_file_viewer/test_video_inspect_loop.py) (439 lines) — `run_video_inspect` / sequence-loop behaviors; owns the single-use `_inspect_layout` and public `os_terminal_size`.
- [test_video_inspect_session.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/ace/tui/artifact_file_viewer/test_video_inspect_session.py) (282 lines) — quiet-terminal handling, session internals, cell rendering.
- [_video_inspect_shared.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/ace/tui/artifact_file_viewer/_video_inspect_shared.py) (42 lines, private) — public `FakeScrub` and `write_clip` needed by more than one module.
- [_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/ace/tui/artifact_file_viewer/_helpers.py) — added public aliases `TEST_IMAGE_AREA`, `strip_ansi`, `test_icat_command`; existing `_`-prefixed importers untouched.
- The facade re-exports all 28 test functions plus `os_terminal_size` via `__all__` with `__test__ = False` (same pattern as `tests/test_agent_hijack_stop.py`), so the original import path keeps working without double collection.

No `_`-prefixed name is imported across the new modules (verified by scan); production monkeypatch targets are unchanged string paths.

Verification observed: collection before/after diff shows identical 28 test names; `pytest` on the four files gives 28 passed; `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` each pass individually; `sase tool run check` triage verdict is pass (`exited_zero`). One note: this session has no SASE slash-skills, so I read the referenced memory notes directly with file tools instead of `/sase_memory_read`, and closed out without `/sase_final`.

Declaration accepted for `commit`. The video-inspect test split is submitted for host commit.
