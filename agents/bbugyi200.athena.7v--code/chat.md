# Chat History - ace-run

- **TIMESTAMP:** 2026-07-13 10:52:34 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 7v--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-7v__plan-260713_102056.md`
- **2. --code** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260713_102056.md`

## Prompt

%model:@codex_coder
#gh:gh_sase-org__sase @sase/repos/plans/202607/runner_launch_admission.md

The above plan has been reviewed and approved. Implement it now.


## Response

I’ll implement the approved plan as written, first reading it end-to-end and checking the current worktree so I can preserve any unrelated changes. Then I’ll make the scoped edits and run the repository’s required `just install` and `just check` verification.

The supplied `@sase/...` path is a workspace-style reference rather than a literal filesystem path here. I’m resolving it within the checked-out repository now; no files have been changed.

I’ve read the approved plan fully. The work is confined to the Python runner-slot policy/lifecycle, ACE status wording, documentation, and tests; it does not require a Rust API or schema change unless the existing scan projection proves insufficient. I’m now mapping the current implementations and regression coverage before editing.

The current scan already exposes each parked waiter’s persisted `wait_runners`, so the Rust boundary remains untouched. I’m applying the policy change by carrying that threshold into the pure queue projection and selecting the oldest waiter that is eligible at the current admitted count; the caller’s current threshold still overrides its own stale projection after a live config edit.

The policy edit is in place. The first focused test invocation exposed a stale/uninitialized workspace environment (`pytest` could not load the configured asyncio plugin), which is exactly why this repository requires installation before checks. I’m installing the workspace dependencies now, then I’ll continue with lifecycle and presentation edits.

Dependency installation is still compiling the local Rust extension; it is progressing normally. While that completes, the next lifecycle edit will move the single admission claim ahead of both primary and linked-workspace preparation, while keeping dependency/time/fork waits and repeat-stop resolution ahead of admission.

The lifecycle is now reordered: dependency/time/fork waits and repeat-stop resolve first; every non-stopped launch then passes the gate once; only after admission does it claim a deferred workspace or prepare primary/linked workspaces. I’m updating the regression tests to assert the new active-runtime semantics, including visibility of `run_started_at` while preparation is deliberately blocked and terminal handling when linked preparation fails.

The reordered lifecycle passes the existing deferred, dependency, and slot suites. One new concurrency-style test harness stalled before reaching its preparation callback because the shared test helper mutates process-global patching state and is not thread-safe. I’m replacing that harness with a deterministic preparation-failure regression that makes the same assertions at the preparation boundary and also verifies terminal error handling.

The ACE snapshot context now computes positions only among waiters eligible at the current admitted count. An ineligible drain barrier is labeled “not currently eligible”; eligible ordering is labeled “eligible queue,” so the UI no longer suggests that the oldest low-threshold waiter blocks everyone. I’ve also replaced the fakey barrier scenario with the approved race: the later high-threshold launch starts first and keeps the drain barrier parked.

The focused policy, lifecycle, fakey, and ACE context/rendering suites are green. I’ve completed the documentation updates, including the new meaning of `BEGIN` and active runtime. I’m formatting the touched sources and docs now, then I’ll run the visual snapshot test because the rendered queue wording intentionally changed.

The visual suite produced the single expected affected case, but it failed before pixel comparison: the longer “eligible queue #2 of 2” phrase is clipped by the fixed-width details panel, so the full SVG substring is absent. I’m inspecting the rendered artifact and will shorten the label while preserving the eligibility distinction before updating any golden.

All 71 focused regressions now pass, including the real fakey admission race, live cap changes, crash/kill recovery, dependency/deferred ordering, child exemption, one-scan uncontended admission, and zero-scan child admission. The targeted visual case also passes exact pixels; the eligibility label is present in the SVG but does not require a golden change at the fixed viewport. I’m starting the mandatory repository-wide `just check` now.

The repository-wide static gates all passed: Python/Markdown formatting, keep-sorted, Ruff, mypy, script lint, Symvision, and file-size checks. `just check` then stopped at an unrelated workspace initialization prerequisite: `sase validate` wants to generate a README and 1.3 MB directory-map image in the linked research companion. That is outside this implementation and would mutate a linked repository, so I’m leaving it untouched and running the full `just test` gate separately to complete code verification.

The full suite is progressing cleanly through roughly 93% of 16,890 tests, including the visual subset. No implementation failures have appeared.

The full test gate passed: 16,884 tests passed and 7 skipped, including all PNG visual snapshots. I’m doing the final worktree/diff audit now to confirm only the approved implementation, tests, and docs changed and that no generated or linked-repository files were touched.

Implemented the approved runner-admission plan.

Key changes:

- Admission is now FIFO among currently eligible waiters; an older `runners=0` barrier no longer blocks higher-threshold work.
- Immediate roots claim admission before primary and linked-workspace preparation.
- Dependency/time/fork waits and repeat-stop remain before admission; children remain exempt.
- ACE displays eligibility-aware queue context and updated drain-barrier wording.
- Documentation and comprehensive lifecycle, policy, fakey, performance, and TUI tests were updated.

Verification:

- `just install` passed.
- 71 focused tests passed.
- Full suite: **16,884 passed, 7 skipped**, including visual snapshots.
- Formatting and all lint/type/static gates passed.
- `just check` only stopped at unrelated `sase init --check` state requesting generated research-companion README/map files; those out-of-scope linked-repository files were left untouched.

The implementation is complete and the finalizer confirms these are this session’s scoped changes. I’m using the `sase_git_commit` skill now to commit exactly the 15 listed files, without touching unrelated work.

The diff audit matches the approved scope: admission policy and lifecycle code, eligibility-aware ACE wording, documentation, and regression coverage only. I’ll commit it as a user-facing bug fix because it corrects launch ordering and when a root begins consuming a runner slot.

Implemented and committed the approved runner-admission changes.

Commit: `d546a813c fix: correct runner launch admission ordering`

The worktree is clean and synchronized with `origin/master`. Full verification previously passed: 16,884 tests passed, 7 skipped.
