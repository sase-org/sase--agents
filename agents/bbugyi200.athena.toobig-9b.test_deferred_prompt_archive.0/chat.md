# Chat History - ace-run (toobig-9b.test_deferred_prompt_archive.0)

- **TIMESTAMP:** 2026-11-04 16:33:07 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-9b.test_deferred_prompt_archive.0

## Prompt

%id:toobig-9b.test_deferred_prompt_archive.0
%clan(toobig-9b, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 769  tests/agents_sync/test_deferred_prompt_archive.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/agents_sync/test_deferred_prompt_archive.py` file into multiple files? Use your best
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

Split done. The 769-line module is now a package that keeps the original import path.

Changed:

- Removed [old test module](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/agents_sync/test_deferred_prompt_archive.py).
- Added [facade](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/agents_sync/test_deferred_prompt_archive/__init__.py:1) re-exporting 10 public tests.
- Added [shared helpers](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/agents_sync/test_deferred_prompt_archive/_helpers.py:1) with public `HostedLinks`, `stub_full_sync`, `OWNER` and others.
- Added [land tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/agents_sync/test_deferred_prompt_archive/test_land.py:1) with private land helpers in-file.
- Added [busy-lock tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/agents_sync/test_deferred_prompt_archive/test_full_sync.py:1) with private `_artifacts_dir` and the `deferred_publication` fixture in-file.
- Added [parity and acknowledgment tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/agents_sync/test_deferred_prompt_archive/test_acknowledgment.py:1).
- Retargeted [planner restore tests](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/agents_sync/test_planner_deferred_restore.py:40) from `_HostedLinks` and `_stub_full_sync` to the new public helpers.

Each new file is under 500 lines. No new module imports a `_`-prefixed name from another new module. The facade exports only public test names.

Verified:

- `pytest` on the new package plus planner restore: 23 passed.
- `just _lint-symvision`: pass.
- `just _lint-mypy`: pass.
- `just _lint-toobig`: pass. Only remaining info is unrelated `test_publication_job.py`.
- `sase tool run check`: 1137 passed, 1 failed. The failure is `test_macro_string_literals_avoid_xprompt_terms` because the generated allowlist still pins the old path. That allowlist file says do not hand-edit, so I left it unchanged.
