# Chat History - ace-run (02d--code)

- **TIMESTAMP:** 2026-08-15 11:12:15 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** 02d--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-02d__plan-260815_104658.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-02d__code-260815_104658.md`

## Prompt

%model:@small_worker
#gh:gh_sase-org__sase @sase/repos/plans/202608/hyphenated_prompt_word_completion.md

The above plan has been reviewed and approved. Implement it now.


## Response

I’ll read the approved plan and the nearby code paths it names, then implement directly against the current checkout. After changes I’ll run the repo’s required verification path.

The plan is narrowly scoped: shared word-token helpers, prompt history extraction, focused tests, and ACE docs. I’m going to inspect those modules now so the change follows the existing completion flow.

The current helper is the only shared range rule for both local and history fallback, so I’ll add an explicit “useful identifier-like word” predicate there and reuse it from history extraction. That keeps tokenization and candidate eligibility from drifting.

I found the acceptance path already delegates replacement ranges back to the shared helper for both local and history words. The implementation should mostly be helper semantics plus tests; no keymap or persisted format needs to move.

I’m going to edit the shared prompt-word helper first, then adjust history extraction to call the new eligibility predicate. After that I’ll add the regression tests and docs wording from the plan.

The helper update is in place. I’m adding tests in the existing pure/widget test files now, including the `bob-ma` history regression and suffix replacement cases.

The history extraction tests now cover whole-token length filtering and numeric/hyphen noise rejection. Next I’m extending the history completion widget tests around the actual `Ctrl+T` flow.

The widget regressions are added. I’m updating the ACE docs now to state the new ASCII-hyphen behavior without changing config names or defaults.

The code, tests, and docs are edited. I’m doing a quick diff scan for formatting issues before running install and the focused test set.

The diff is scoped to the planned files. I fixed one obvious line-length issue and am starting the required environment install before tests, per the repo instructions.

Install completed cleanly. I’m running the focused test files from the plan now.

The focused suite passed: 55 tests. I’m moving on to `just check` for the repo-required lint/type/scoped test gate.

`just check` stopped at Ruff formatting in one helper expression. I’ll format that file and rerun the gate.

Formatting is fixed. I’m rerunning `just check` now.

`just check` has cleared formatting, markdown, keep-sorted, Ruff, and mypy; the remaining scoped test work is still running.

The remaining lint checks are passing incrementally. I’m waiting for the scoped test selector and test lane to finish.

`just check` is still active with no new output in the last poll. I’m continuing to wait rather than interrupting the required gate.

`just check` reported the existing core-floor probe warning about the declared `sase-core-rs==0.27.2` floor missing newer capabilities, but the gate continued past it and has not failed. I’m waiting for the final status.

No final result yet; `just check` is still running. I’ll keep polling until it exits.

The check gate is taking longer in the scoped test phase, but it is still live. I’m not starting any other repo-mutating work while this required run is in progress.

`just check` passed, including the scoped test lane. It did surface a non-failing “stale_actionable” core-floor probe message; per the project instructions I’m checking whether that should be recorded as a duplicate-safe follow-up bead before I wrap up.

I’m using the `sase_new_task` workflow for that follow-up check because the repo instructions require duplicate-safe handling before recording discovered work.

I’ve loaded the bead and sizing policy. I’m searching for an existing task or active epic tied to the stale core-floor warning before deciding whether to create anything.

The stale-floor probe is not a duplicate of the older task-wire floor task: it names newer proc lifecycle and query-profile capabilities. There are active epics with direct ownership, so I’m routing the evidence there as notes instead of creating a new task bead.

I’ve added the routing notes to the two active epics; the bead commands are still settling. I’ll wait for both to finish and then verify the working tree.

The discovered follow-up evidence has been routed to the active owning epics, so no new task bead was created. I’m checking the final repo status and diff now.

The final diff is six planned files, and `git diff --check` is clean. I’m doing one final targeted source scan before the closing summary.

Implemented the approved plan.

Changed:
- [prompt_word_completion.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/ace/tui/widgets/prompt_word_completion.py): ASCII hyphens are now part of prompt word ranges, with hyphen-only runs filtered out as candidates.
- [prompt_words.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/history/prompt_words.py): history extraction keeps full hyphenated spellings and rejects hyphen-only / numeric-hyphen noise like `123-456`.
- Added focused local/history completion regressions for `bob-ma` → `bob-mac-capture`, shared-prefix refresh, and right-hand suffix replacement.
- Updated [docs/ace.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/docs/ace.md) to document ASCII-hyphen word completion behavior.

Verification:
- `just install` passed
- `.venv/bin/pytest tests/ace/tui/widgets/test_prompt_word_completion.py tests/ace/tui/widgets/test_history_word_completion.py tests/history/test_prompt_words.py` passed: 55 tests
- `just check` passed

`just check` also emitted a non-failing stale core-floor probe warning unrelated to this diff; I routed that evidence to the active owning epics instead of creating a new task bead.

I’m at the finalizer step. The listed changes match the completed implementation, so I’m going to use the required SASE commit workflow now and then report the commit result.

The commit workflow is recorded. I’m checking the dirty tree and diff now so the commit message matches only these changes.

The diff is exactly the planned six files: production helper semantics, history extraction, focused tests, and ACE docs. I’m writing a conventional `fix` commit message and committing all dirty paths through `sase_git_commit`.

The primary commit has succeeded; the wrapper is still returning control after its post-commit bookkeeping. I’m polling it to completion, then I’ll verify branch status.

The commit wrapper exited successfully with a queued publication warning, not a commit failure. I’m checking whether the repository is clean and whether the commit was pushed.

Committed the implemented changes with `sase_git_commit`.

Commit: `435cb34df fix: complete hyphenated prompt words`

Working tree is clean and not ahead of `origin/master`. The commit wrapper reported that primary commit succeeded; prompt/archive publication had a non-blocking queued/sync-lock warning.
