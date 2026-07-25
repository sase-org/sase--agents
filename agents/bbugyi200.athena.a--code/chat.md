# Chat History - ace-run

- **TIMESTAMP:** 2026-07-06 13:32:12 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** a--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-a__plan-260706_130018.md`
- **2. --code** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260706_130018.md`

## Prompt

%model:@claude_coder
#gh:gh_sase-org__sase @/home/bryan/.sase/plans/202607/humanize_prompt_display_surfaces.md

The above plan has been reviewed and approved. Implement it now.


## Response

I’ll read the approved plan and current repo state first, then map the requested changes to the existing code paths before editing.

The plan touches ACE TUI rendering and filter paths, so I need to load the repo’s TUI performance memory through the required SASE memory-read procedure before changing those areas.

Using `sase_memory_read` for `memory/tui_perf.md`, because this change touches TUI render and filter behavior.

I’ve loaded the perf rules. Next I’m tracing the existing humanization helpers and the specific modal/widget call sites so the edits stay presentation-only.

The existing helper already has the right cached display-name map; the loader still has a private uncached attach path. I’m now reading each affected surface in smaller chunks so the change can reuse that helper consistently.

The modal code confirms the plan’s scope: most storage reads stay untouched, and the UI currently feeds raw prompt/chat text straight into summaries, filters, and renderables.

The prompt panel needs a little care because it has a render cache and can paint large response content. I’m checking the adjacent reply/attempt helpers before adding a small memoized humanize step.

There are existing tests around these surfaces, so I’ll extend those instead of creating broad new fixtures where possible.

The dismissed bundle API is central enough that I’m checking its persistence tests before patching it; the goal is to attach display-only fields after rehydration without changing serialized bundles.

The tests give us useful seams: we can assert the new behavior with lightweight object-level tests for helpers and modal methods, then rely on existing integration fixtures for persistence.

The `project_display_name` field is already serialization-excluded, so the attach helper can be safely called after bundle loading; the bundle file contract should remain unchanged.

I’m going to make the shared attach helper project-agent aware so ordinary CL agents do not trigger unnecessary display-name map work when they have a project file but do not display as the project itself.

I have enough context to implement in four passes: add the shared attach/display helpers, patch the modal/widget/CLI display boundaries, extend focused tests, then run `just install` and `just check` as required.

I’m starting with the shared helper and loader wiring. This keeps all downstream display code using the same cached project-name source.

One detail in the bundle loader: partial results from a cancelled/shutdown executor also need the display-only field attached, since callers can still render those partial rows.

Next I’m patching the prompt-history item model and render paths so each record keeps canonical storage text while carrying a separate humanized display string.

I’m wiring the prompt-history preview and filter code to read from the display field only where it is shown or returned to the user; the underlying `entry.text` stays canonical.

For prompt-history filtering, I’m matching both what the user sees and the canonical stored text so old queries remain findable.

I’m applying the same boundary rule to the revive modal: row names come from attached agent display names, and response preview/filter text is humanized without touching the agent artifacts.

For revive filtering, I’m including the humanized response text and retaining canonical label terms so searches do not get narrower.

The run-log detail pane truncates before rendering, so I’m humanizing those bounded text blocks after truncation.

I’m changing the prompt panel so every markdown path runs through one cached humanization function before the existing lazy render cache sees the content.

Saved-group previews store old display strings, so I’m mapping those at render time and humanizing the prompt preview text there only.

For `sase prompt list`, I’m keeping JSON stable and changing the pretty table’s hints and preview text, which are the user-facing display columns called out by the plan.

The primary display paths are patched. I’m doing a quick static scan now for the old raw render calls and then I’ll add tests around the changed behavior.

A static scan found the prompt-panel hint mode has parallel raw prompt/chat reads. The approved plan did not call it out, but it is the same display surface, so I’m checking it before deciding whether to patch it too.

Hint mode is also a prompt display path, so I’m patching it with the same helper. It is on-demand rather than per-paint, so the global cached map is enough here.

Whitespace checks are clean. The broader scan pattern was too loose for `rg`, so I’m rerunning it with simpler searches.

The workflow detail renderer has a separate markdown prompt render path. Since it displays stored prompt text too, I’m checking whether it needs the same boundary handling.

I’m also patching workflow prompt rendering; it is another prompt panel display path and the same storage/display rule applies.

The workflow renderer imports are slightly different; I’m applying the same small change against that file directly.

I’m adding focused tests now. First is the shared attach helper, including the important “bundle serialization stays canonical” behavior through the dismissed loader.

For prompt history, I’m testing list rows, filtering, preview, and load-to-input behavior against a separate `display_text` field so canonical history entries remain unchanged.

For revive, I’m covering row labels, metadata headers, response previews, and filtering in one set of lightweight tests using the modal rendering helpers.

For the run-log modal, I’m testing `_update_detail` directly with a fake Static widget; that exercises the actual section-building code without running the TUI.

I’m tightening one test type annotation now so mypy does not infer the fake widget’s captured value as a bare `object`.

For saved groups, I’m testing render-time mapping of stale saved names and prompt previews.

That saved-group test needs to isolate the changed ref line; summary titles can still contain arbitrary archived text, so I’m keeping the fixture title neutral.

The prompt-panel xprompt test relied on the agent’s attached display field. Since the implementation now uses the global cached map to support multi-project prompts, I’m updating that test and adding prompt/chat coverage.

I also added workflow prompt rendering behavior, so I’m adding a compact assertion in the existing workflow-display test file.

For the CLI, I’m testing the pretty list output through the module-level humanize hook so the test stays focused on `prompt list` display behavior rather than project-record setup.

The loader path also attaches display names to loader-sourced dismissed agents. I’m checking the pure apply-boundary tests to add a direct guard for that behavior.

I’m adding a direct pure-function guard for loader-sourced dismissed agents so the revive/run-log list has the attached display name even before bundle paging is involved.

One small performance fix: if a text block has no `#`, the panel can skip the map signature and regex path entirely.

The implementation pass is complete; I’m moving into formatting/static checks and focused test runs now.

Per repo instructions, I’m running `just install` before any checks because this workspace may be stale.

`just install` failed before Python checks because the linked `sase-core` workspace for this workspace is stale (`0.3.0` while this repo requires `>=0.3.2`). I’m opening the linked workspace through SASE’s required command so the install can use the correct linked checkout.

The linked core workspace updated successfully. I’m retrying `just install`.

`just install` is still building the Rust extension; I’m waiting for it to finish before running targeted tests.

The install is still compiling `sase_core_py`; no failures yet.

Install succeeded. I’m running focused tests for the touched surfaces plus a targeted Ruff pass before the full `just check`.

`uv run` is blocked by an existing `uv.lock` ambiguity around `sase-core-rs`; the editable environment is installed, so I’m running the same tools directly from `.venv/bin`.

The failing test used `#gh:project.` with the period immediately attached; the existing VCS-ref parser treats `.` as part of possible refs. I’m adjusting the test fixture to the parser-supported boundary form rather than changing parser semantics in this display-only patch.

The focused Ruff pass passed. I’m rerunning the focused pytest set after the test fixture adjustment.

Focused tests are passing. I’m running the required full `just check` now.

`just check` has passed formatting, linting, mypy, and SASE validation; the test portion is still running.

The full test suite is still running under `just check`; no new failures have printed.

Still waiting on the test suite. The earlier stages are done, so this is the long pytest/visual segment.

`just check` completed successfully. I’m doing a final diff/status pass to summarize exactly what changed.

The final status only shows the intended source and test files modified in the SASE repo.

Implemented the approved plan.

Key changes:
- Added shared display-name attachment/cache helpers in [project_display_names.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/project_display_names.py).
- Attached `project_display_name` for dismissed/revived agents without serializing it.
- Humanized VCS project refs at display boundaries for prompt history, revive modal, run log, prompt panel, workflow prompt panel, saved group revival, and `sase prompt list`.
- Kept stored prompt history, bundles, artifacts, and launch canonicalization canonical.
- Added focused tests across the touched surfaces.

Verification:
- `just install` passed after refreshing the linked `sase-core` workspace required by this repo.
- Focused pytest set passed: `34 passed`.
- Required `just check` passed, including fmt, lint, mypy, validation, and full tests.

Using `sase_git_commit` now because the finalizer found uncommitted changes from this implementation and requires a SASE commit. I’ll verify the current status, then commit only the listed files.

The commit skill is logged. I’m checking the working tree and diff now so the commit message and staged file list match the actual changes.

Status matches the finalizer list. I also see the branch is one commit behind upstream, so after committing I’ll need to let the SASE commit flow handle sync or resolve any push/rebase result before declaring it done.

The diff is the expected display-boundary work: shared display-name helpers, TUI/CLI humanized render paths, and focused tests. I’m writing a narrow `fix` commit message and staging exactly those files with repeated `-f` flags as required.

The commit message file is ready. I’m running the SASE commit wrapper now; if it needs to sync with upstream, I’ll handle the result before finishing.

The SASE commit completed successfully. I’m doing the required post-commit status check now to confirm the worktree is clean and the branch is not left ahead.

The branch status is clean and aligned with `origin/master`. I’m grabbing the commit id so I can include it in the closeout.

Implemented and committed the approved plan.

Commit: `228fc78af fix(tui): humanize project refs in prompt displays`

Summary:
- Humanized VCS project refs across prompt history, revive/run-log modals, prompt panels, saved group previews, and `sase prompt list`.
- Kept persisted prompt/bundle data canonical.
- Added focused coverage for the new display behavior.

Verification completed earlier: `just install`, focused tests, and required `just check` all passed. Post-commit status is clean and aligned with `origin/master`.
