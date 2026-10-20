# Chat History - ace-run (toobig-89.test_collect_qualification_jobs.0)

- **TIMESTAMP:** 2026-10-20 07:06:22 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** toobig-89.test_collect_qualification_jobs.0

## Prompt

%id(test_collect_qualification_jobs.0, clan=toobig-89)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_collect_qualification_jobs.py` file into multiple files? Use your best
%wait:toobig-89.test_ace_png_snapshots_agents_deck_views.0
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

Split complete. The 842-line `tests/test_collect_qualification_jobs.py` is now a 59-line facade plus three focused modules and one shared helper module, each under 500 lines.

What changed:

- [tests/_collect_qualification_jobs_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/_collect_qualification_jobs_helpers.py) (231 lines): shared builders with public names (`qualification_manifest`, `qualification_entries`, `qualification_job_row`, `write_job_pages`, `write_artifact_pages`, `blocking_artifact_names`, `write_pass_evidence`, `run_collect`, `check_names_for_attempt`), constants (`ROOT`, `SCRIPT`, `INVENTORY`), and the `tool`/`release_tool` fixtures. Split files import only these public names.
- [tests/test_collect_qualification_jobs_bundle.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/test_collect_qualification_jobs_bundle.py) (249 lines): success, caller-prefix scope, rerun carry-forward, duplicate rows.
- [tests/test_collect_qualification_jobs_evidence.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/test_collect_qualification_jobs_evidence.py) (259 lines): missing/expired/harness typing, advisory, streaming pages, live-supersedes-tombstone.
- [tests/test_collect_qualification_jobs_fetch.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/test_collect_qualification_jobs_fetch.py) (235 lines): noncontiguous/malformed/duplicate refusals plus both fetch-evidence tests. The `patch_gh_transport` helper (used only here) lives in this file, so the monkeypatch target (`tool._run_gh`) keeps working unchanged.
- [tests/test_collect_qualification_jobs.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/test_collect_qualification_jobs.py) (facade): re-exports all 14 public test names plus `ROOT`, `SCRIPT`, `INVENTORY`, `tool`, `release_tool`. No `_private` re-exports. `__test__ = False` so tests run once via the split modules.

Verification:

- 14 split tests pass; facade collects 0 (import path preserved, no double-run).
- `just _lint-symvision`: pass. `just _lint-mypy`: pass.
- `just _lint-toobig`: red only on pre-existing `tests/test_release_watch_health.py` (1253 lines, untouched by this split); none of the five split-touched files are flagged.
- `sase tool run check`: exit 0 (after a `ruff format` fix on the new files).

Declaration submitted for the test split commit.
