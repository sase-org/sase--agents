# Chat History - ace-run (toobig-2o.split_file.src.sase.llm_provider.commit_finalizer_git.0)

- **TIMESTAMP:** 2026-08-14 13:25:37 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-2o.split_file.src.sase.llm_provider.commit_finalizer_git.0

## Prompt

#gh:sase-org/sase
%id:toobig-2o.split_file.src.sase.llm_provider.commit_finalizer_git.0
%clan(toobig-2o, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 711  src/sase/llm_provider/commit_finalizer_git.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/llm_provider/commit_finalizer_git.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by reading the file to understand its structure.

Now let me find all consumers of this module.

Now let me write the new modules.

Now the git command/status module:

Now the progress/evidence module:

Now the facade:

Now update the callers and tests.

Now the two tests that reach for private helpers:

Install finished. Running the checks now.

Symvision doesn't count module-attribute access as a use. Switching the progress module to direct imports:

Lint is clean. Now the tests:

Pre-existing failure — it fails identically on the unmodified tree. Let me confirm it isn't already fixed upstream:

Lint passes and the scoped suite is green except for one pre-existing failure unrelated to the split. Let me file that as a task bead.

Exact duplicate already exists (`sase-m2`). Let me corroborate it instead:

Done. `src/sase/llm_provider/commit_finalizer_git.py` (711 lines) is now five files, all well under 500:

| File | Lines | Responsibility |
|---|---|---|
| `commit_finalizer_git.py` | 50 | Aggregate entry point — re-exports the public API |
| `commit_finalizer_git_paths.py` | 70 | Path classification: reserved SASE paths, prompt-archive matching, normalization |
| `commit_finalizer_git_status.py` | 246 | Git subprocess primitives + working-tree status/fingerprint queries |
| `commit_finalizer_git_progress.py` | 188 | Progress fingerprints and discarded-dirty-work evidence |
| `commit_finalizer_git_autocommit.py` | 285 | Narrow, provably-safe SDD auto-commits |

**Design notes**

Keeping `commit_finalizer_git.py` as a re-export facade meant zero churn in `commit_finalizer.py`, `commit_finalizer_state.py`, `commit_finalizer_baseline.py`, and most tests.

Symvision forbids importing `_`-prefixed names across files, so genuinely shared helpers were promoted to public names in their new homes: `_run_git`→`run_git`, `_git_status_records`→`git_status_records`, `_git_show_head_file`→`git_show_head_file`, `_git_head_commit_id`→`git_head_commit_id`, `_changed_files_from_git_status`→`changed_files_from_git_status`, `_GitStatusRecord`→`GitStatusRecord`, plus `normalize_status_path` / `is_sase_reserved_status_path`. Helpers used only within one file stayed private. `_new_commit_messages` kept its revision-range logic in the progress module and now calls a generic `git_log_commit_messages` primitive.

One subtlety worth flagging: `tests/llm_provider/_codex_fallback_helpers.py` monkeypatches `_git_head_commit_id` by module path, and Symvision only counts *direct imports* as usage — so the progress module imports the name directly rather than accessing it through the module object, and the patch target moved to `commit_finalizer_git_progress.git_head_commit_id`. Patching the definition module would have been a silent no-op.

**Verification**

`just lint` is fully clean. `just check`'s scoped test lane leaves exactly one failure: `test_pre_existing_sibling_file_is_excluded_and_reported_separately`, which **fails identically on the unmodified tree** (confirmed by stashing) and isn't fixed by the two upstream commits this branch is behind. It was already filed as `sase-m2`; I added a +1 with my independent reproduction rather than opening a duplicate.

I'll commit the changes now.

Committed as `338f1bd75`. Working tree is clean and `master` is in sync with `origin/master` (the commit rebased cleanly onto the two upstream commits the branch was behind).

## What landed

`src/sase/llm_provider/commit_finalizer_git.py` (711 lines) is now five files, all under 500:

| File | Lines | Responsibility |
|---|---|---|
| `commit_finalizer_git.py` | 50 | Aggregate entry point — re-exports the public API |
| `commit_finalizer_git_paths.py` | 70 | Path classification: reserved SASE paths, prompt-archive matching, normalization |
| `commit_finalizer_git_status.py` | 246 | Git subprocess primitives + working-tree status/fingerprint queries |
| `commit_finalizer_git_progress.py` | 188 | Progress fingerprints and discarded-dirty-work evidence |
| `commit_finalizer_git_autocommit.py` | 285 | Narrow, provably-safe SDD auto-commits |

Keeping the original module as a re-export facade meant zero churn in `commit_finalizer_state.py`, `commit_finalizer_baseline.py`, and most tests.

Symvision forbids importing `_`-prefixed names across files, so genuinely shared helpers were promoted to public names (`_run_git`→`run_git`, `_git_status_records`→`git_status_records`, `_changed_files_from_git_status`→`changed_files_from_git_status`, and friends); single-file helpers stayed private. One subtlety: `tests/llm_provider/_codex_fallback_helpers.py` monkeypatches the head-commit lookup by module path, so the patch target moved to `commit_finalizer_git_progress.git_head_commit_id` — patching the defining module would have been a silent no-op.

## Verification

`just lint` is fully clean. `just check`'s scoped test lane leaves exactly one failure, `test_pre_existing_sibling_file_is_excluded_and_reported_separately`, which I confirmed fails identically on the unmodified tree via stash. It was already filed as task bead `sase-m2`; I added a corroborating +1 rather than opening a duplicate.
