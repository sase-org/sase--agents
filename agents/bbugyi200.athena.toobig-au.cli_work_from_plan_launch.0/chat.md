# Chat History - ace-run (toobig-au.cli_work_from_plan_launch.0)

- **TIMESTAMP:** 2026-11-27 20:47:44 EST
- **MODEL:** codex/gpt-6-luna
- **AGENT:** toobig-au.cli_work_from_plan_launch.0

## Prompt

%id:toobig-au.cli_work_from_plan_launch.0
%clan(toobig-au, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[bold #FFAF5F]◆ 903  src/sase/bead/cli_work_from_plan_launch.py[/bold #FFAF5F]
[#87D7FF]• 816  tests/test_staged_inactive_host.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/bead/cli_work_from_plan_launch.py` file into multiple files? Use your best
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

I’ll map the module’s responsibilities and its tests first, then split it into cohesive modules while preserving `cli_work_from_plan_launch` as the public import path. I’ll run each requested lint command separately, fix all touched-file findings, and finish with `sase tool run check`.

The file is 903 lines and has three clear responsibilities: the locked archive/create transaction, linked-epic resume handling, and the publication-conflict replay recovery flow. I’m checking test patch points and existing module conventions now so the facade preserves callers and monkeypatch behavior. I’ll also consult the required lint/test memory before the final checks.

The only private-name dependency exposed to tests is `_replay_publication_conflict`. I’ll move that behavior to a private implementation module under the public helper name `replay_publication_conflict`, and retarget those tests to the implementation module. The original module will remain a small facade exporting its existing public API.

The split is in place: the launch transaction is 495 lines, replay recovery is 252, shared launch operations are 170, and the original path is now a 15-line facade. Formatting completed; I’m moving through the three requested lint gates one at a time, then I’ll start the wrapped `check` run.

Symvision passed after making the one same-module helper private. Mypy found that extracting the resume wrapper had dropped its import of the existing resume implementation; I’m restoring that import and will rerun mypy before the line-count gate.

Mypy now passes. The toobig command passes for `src` and all split files, but the test-tree gate reports a pre-existing 1,366-line `tests/test_staged_inactive_host.py`, which this split did not touch. I’m doing a final diff review and rerunning Symvision against the final imports before the requested wrapped check.

The review confirms the facade exports only the original `__all__` API; the replay helper is available by its public name only inside private implementation modules, and the tests now patch that implementation seam directly. I’m rerunning Symvision after the import fix, then I’ll launch `sase tool run check` under the monitor workflow because that check can exceed the turn’s inline window.

The final Symvision rerun passed, and `sase tool run check` is still progressing through repository-wide checks; so far its formatting, Ruff, mypy, and feature-flag stages have completed. I’m waiting for its test lane and final result.

The wrapped check has also completed Symvision and the documentation/SASE validation stages. It is still running the remaining `check` work; the check’s run ID is `843b445975c90ebf321e3fe46db9dacd`.

The check is past all reported lint and validation stages and is quiet while its remaining lane runs. There’s no error output so far; I’m letting the same run finish rather than restarting it.

The `check` test lane is still active and has now reported a six-minute duration; host load is high, but the run remains live and has not escalated or failed. I’ll continue following this same run.

The requested `sase tool run check` completed successfully, including the scoped tests. Final file lengths are 15, 498, 171, and 250 lines. The standalone toobig gate’s only failure is the unrelated existing oversized test file; I’m submitting the SASE turn finalizer now.

Split `cli_work_from_plan_launch.py` into a facade and three private implementation modules. The original public import path remains available, and all four resulting files are under 500 lines. Retargeted tests to the new replay helper.

**Verification:** `sase tool run check` passed, including scoped tests. Symvision and mypy passed. `just _lint-toobig` found one unrelated existing violation: `tests/test_staged_inactive_host.py` has 1,366 lines. The split files are all within the limit.
