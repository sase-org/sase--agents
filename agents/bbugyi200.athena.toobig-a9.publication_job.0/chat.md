# Chat History - ace-run (toobig-a9.publication_job.0)

- **TIMESTAMP:** 2026-11-19 19:42:59 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-a9.publication_job.0

## Prompt

%id:toobig-a9.publication_job.0
%clan(toobig-a9, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 4 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 815  src/sase/axe/_state_scheduler.py[/#87D7FF]
[#87D7FF]• 774  src/sase/agents_sync/publication_job.py[/#87D7FF]
[#87D7FF]• 717  tests/ace/tui/util/test_gc_telemetry.py[/#87D7FF]
[#87D7FF]• 706  tests/ace/tui/test_launchable_mru.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/agents_sync/publication_job.py` file into multiple files? Use your best
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

Split `publication_job.py` (774 lines) into a facade plus three focused modules, all under 500 lines. Behavior and the public import path are preserved.

New layout in [src/sase/agents_sync](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/agents_sync):

- [_publication_job_shared.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/agents_sync/_publication_job_shared.py) (99 lines) — `PublicationJobSummary`, `ProjectPass`, readiness and safe outbox probes shared by both passes.
- [_publication_job_drain.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/agents_sync/_publication_job_drain.py) (265 lines) — public `drain_project` plus its hood/link/referenced-by helpers.
- [_publication_job_run.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/agents_sync/_publication_job_run.py) (442 lines) — public `run_publication_job`, `PUBLICATION_JOB_WORK_BUDGET_SECONDS`, scheduler loop, lock, and standing counters.
- [publication_job.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/agents_sync/publication_job.py) (13 lines) — facade re-exporting only the two public names.

Rules honored: no `_`-prefixed name is imported across the new modules (shared state lives in the already-private shared module under public names); single-use helpers stayed in their consumer module; tests that patched or called private names were retargeted to the owning module (patching `job_run.drain_project` at its lookup site, not the defining module).

Verification, all observed:

- `just _lint-mypy` — clean, no issues in 6637 files.
- `just _lint-toobig` — clean, all files under limits.
- `just _lint-symvision` — no issues in touched files; the two reported symbols (`LaunchPromptContext`, `OutboxGroup`) are in untouched files and reproduce identically on the pristine tree (verified via stash), so pre-existing.
- 51 tests across `test_publication_job.py`, `test_publication_standing.py`, `test_publication_diverged_replay.py`, and `test_parking.py` — all pass.
- `sase tool run check` — every stage passes except the pre-existing symvision pair (1 KNOWN with witness, 1 NEW-but-proven-pre-existing).

Final declaration accepted for commit; the host commits after this turn.
