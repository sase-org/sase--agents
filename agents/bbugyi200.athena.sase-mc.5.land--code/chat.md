# Chat History - ace-run (sase-mc.5.land--code)

- **TIMESTAMP:** 2026-08-15 18:54:00 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-mc.5.land--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_mc_5_land__plan-260815_165802.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_mc_5_land__code-260815_165802.md`

## Prompt

%model:@small
#gh:gh_sase-org__sase
@sase/repos/plans/202608/preserve_models_selection_during_provider_snapshot.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll implement the approved plan to keep the Models-panel selection stable when a provider snapshot finishes. First I'm reading the plan context and locating the snapshot/highlight path.

The plan is small and specific. Next I’ll load TUI performance notes and inspect the Models-panel snapshot/highlight code.

The highlight restore lives in the Models panel and provider snapshot worker. I'll read those paths and the existing navigation tests next.

The race is clear: snapshot completion rebuilds rows with `keep=None` and jumps to the first launch row. I’ll read the routing tests and helpers to see how to preserve the current highlight.

I'll preserve the current highlight when a snapshot finishes without an explicit keep, then add a delayed-snapshot regression around the launch-row reorder.

Next I’ll add the delayed-snapshot regression plus explicit-keep and missing-row fallback coverage.

The production path is in place. I’ll tighten the test helpers, then install and run the focused Models/provider suite.

`LaunchModelField` isn’t re-exported from config, so I’ll import it from the launch-settings module.

The first-paint highlight is `setting:default_effort` because launch rows are not loaded yet. I’ll only preserve a selection the user actually moved, so the initial snapshot can still land on the first launch row.

Focused suite is green (56 passed). Next I’ll find any remaining Models/provider-disable tests, then run `just check`.

Focused Models/provider tests passed. Running `just check` next for the required repo lane.

`just check` failed on a stale Symvision epic symbol, not on the Models-panel change. I’ll confirm that and file a follow-up if it’s already a known issue.

The earlier scoped run escalated because of a stale core-identity signal; current selection is 59 files and stays in budget. I’m stopping that full suite and running the real scoped set.

Provider snapshot completion no longer steals a Models-panel selection the user has already moved.

**What changed**

When a snapshot worker finishes without an explicit `keep` target, the panel now keeps a user-moved cursor. If that row is gone, the existing first-enabled fallback still applies. Explicit keep values from write-driven refreshes still win.

The first-paint cursor is special: launch-setting rows are not on the list yet, so the implicit highlight sits on `setting:default_effort`. Completing that first snapshot still lands on `launch:default_model`. Only a row the user actually moved is preserved. Provider-state reads stay on the thread worker.

**Tests**

- Delayed initial snapshot: hold the worker until `bucket:research` is selected, then let launch rows prepend. The bucket stays selected and `e` still shows `Press l/enter to open this bucket`.
- Explicit `keep="plain"` still wins over the current row.
- A removed bucket falls back to `launch:default_model`.

**Verification**

- Focused Models/provider suite: 56 passed, including the full `test_alias_actions_on_bucket_are_guarded` matrix.
- Diff-scoped lane: 59 files, 723 passed. No escalation on the current tree.
- `just check` lint/format/mypy/validation stages passed except **symvision**, which fails on a stale `--epic-symbol 'sase-m9.3.1.2(compare_inventory_to_source)'` after that phase closed. That is unrelated to this change. I recorded it as a discovered issue on in-progress epic `sase-m9.3.1` instead of creating a new task.

The plan is already implemented; this pass needs to close `sase-mc.5` and commit. I'll read the commit/bead skills and inspect the working tree first.

Uncommitted Models-panel work is present. Next I’ll read bead-close rules and the diffs, then close `sase-mc.5` and commit.

Closing `sase-mc.5` with the verification note, then committing.

The close command is still running. I’ll wait for it to finish before committing.

Bead `sase-mc.5` closed and published. Next I’ll record the commit skill and write the message.

Commit succeeded. Checking that the branch is clean and in sync with upstream.

Closed `sase-mc.5` and committed the Models-panel snapshot-selection fix.

**Commit:** `5511f04ed` — `fix(tui): keep Models selection across provider snapshots`  
Branch is clean and in sync with `origin/master`.

Provider snapshot completion no longer steals a Models-panel row the user has already moved. Implicit snapshots keep that cursor; if the row is gone, the first launch row is used. Explicit keep values from write-driven refreshes still win. The first-paint cursor on `setting:default_effort` is left unset so the initial snapshot can still land on `launch:default_model`.

Bead close published successfully. Prompt-archive publication was skipped because `raw_xprompt.md` is unavailable; that does not affect the commit.
