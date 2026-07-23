# Chat History - ace-run

- **TIMESTAMP:** 2026-07-06 15:22:05 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** a.f1--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-a_f1__plan-260706_142311.md`
- **2. --code** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260706_142311.md`

## Prompt

%model:@claude_coder
#gh:gh_sase-org__sase @sdd/tales/202607/eradicate_raw_project_keys.md

The above plan has been reviewed and approved. Implement it now.


## Response

I’ll read the approved plan and the surrounding code before editing, then I’ll apply the changes and run the repo checks required by the workspace instructions.

This touches TUI render and prompt paths, so I need to follow the repo instruction and read the SASE memory through the audited memory skill before changing those areas.

I’m using `sase_memory_read` for `tui_perf.md` because the approved work changes TUI rendering/prefill paths.

I’m going to trace the existing display-name helpers and the listed surfaces now, then I’ll make the helper additions first so the rest of the edits stay consistent.

The existing helper only rewrites VCS tags, not ChangeSpec-style name prefixes. I’m checking the call sites listed in the plan so I can add the new helper once and use it at presentation boundaries.

I’ve found several direct `cl_name` display paths and prompt relaunch paths. Next I’m opening the CLI and ChangeSpec naming code so the changes stay split between display-only rewriting and canonical storage.

I’ve confirmed relaunch currently mounts stored prompts verbatim, which is one of the remaining edit/paste leaks. I’m now checking the command-line renderers and prompt history helpers.

For CLI output I’m preserving JSON and raw/export paths as canonical, but changing plain/table/clipboard text. I’m also checking prompt search/show/copy because those have several separate render paths.

Prompt `show -f raw` already remains byte-exact, while markdown/full search can share one humanized renderer. I’m checking the name-generation and notification/display paths next because they determine both future names and legacy raw-name cleanup.

The future-name path uses the canonical project key before reservation, so I’ll change only the generated ChangeSpec name there and leave routing/reservation files canonical. Legacy lookup/rendering still needs helper use at display points.

I’m seeing a broad set of possible `cl_name` consumers, but the highest-risk/user-facing ones are concentrated in the approved list. I’ll implement those plus the core model fallback so inherited row labels clean up without touching storage or identity.

I’m starting with the shared helper and tests. The helper will use the cached directory-key map and rewrite exact keys or leading `<key>_` prefixes, preferring the longest key so nested-looking names behave deterministically.

I’m editing `project_display_names.py` now and adding direct unit coverage for exact-key, prefix, longest-match, unknown, and empty-map behavior.

The helper and tests are in place. I’m moving through the TUI surfaces now: commits/file labels, completion metadata, modal rows, runner labels, fork/wait tags, relaunch prompts, and prompt copy.

For commit/file labels, I’m humanizing at the source function that feeds both the COMMITS group and `CommitDiffInfo`, so the primary-group comparison and file panel labels stay consistent.

For agent completion, I’m keeping the inserted agent name unchanged but humanizing the VCS badge and snippet. I’m also adding canonical aliases into `search_text` so filtering can still match the stored raw form.

I’m updating modal rows to render display names while leaving the stored row indices and navigation targets unchanged.

For the tmux workspace chooser, I’m changing only the visible current-row label and project field; the workspace target/window metadata stays as before.

In the runners modal, I’m humanizing labels as they’re rendered, not in the jump target, so the jump still resolves by the canonical name.

For fork/wait prefill, the right choke point is `_resolve_vcs_tag`. I’m humanizing the tag after any smart ref replacement, so all fork and wait callers get the display ref without changing the stored prompt.

One important gap: VCS-tag humanization only handled exact project refs. I’m extending the alias rewrite functions to handle leading `<project>_` ref prefixes too, so display-prefixed legacy ChangeSpec names can round-trip back to canonical at launch.

I’m now wiring that VCS-tag humanization into fork/wait and cleaning the wait-relaunch confirmation label.

For quick launch, I’m separating the canonical `cl_name` passed to launch-prefix construction from the visible selection/bar labels.

Quick launch now uses display refs for visible prefixes, while repeat-selection data still keeps canonical project identity where it already did.

For retry/kill-edit relaunch, I’m converting only the prompt text loaded into the editable bar and the bar label. The captured raw prompt variables and stored files remain untouched until submission.

I’m changing prompt clipboard copy to copy the same human-readable VCS refs the prompt history copy already uses.

I’m updating the `Agent.display_name` fallback now, since many row/detail surfaces go through that property rather than their own label builder.

This model change is display-only: identity fields still hold canonical names, but the default visible label no longer exposes a raw project-prefix legacy name.

I’m moving into CLI renderers now. The pattern is: JSON/raw/export stay canonical; table, markdown, picker, preview, and clipboard text get humanized before display/copy.

For the legacy prompt-history fzf picker, I’m adding a stable row prefix derived from the prompt text hash so selection is resolved by that prefix instead of by parsing the humanized preview text.

I’m checking existing prompt-history tests before changing the fzf display shape, because that shape may have compatibility expectations.

I’ll keep the storage-layer fzf formatter compatible and add the stable numeric prefix only in the picker that needs it. That avoids broad display-shape churn.

For `changespec current`, I’m humanizing only the plain/markdown/diagnostic strings; the JSON payload continues to carry canonical `name`, `project`, and `parent`.

I’m patching the ChangeSpec current renderer and also the ambiguous-match error line so every human string there uses the same name helper.

I’m removing the raw `key=...` fragment from the human workspace listing and using the display project name in the header. JSON still includes `project_key`.

Prompt search compact snippets are being humanized after choosing the matching raw snippet window, so searches against canonical text still show the relevant line without printing the canonical key.

For `prompt select`, I’m humanizing only the preview column; selected records are still resolved by the leading prompt id.

For the older query-editor history picker, I’m making its display formatter human-readable and resolving selection by a numeric prefix added at picker time.

Prompt stats JSON keeps the stored preview, but the pretty “Largest Prompts” table gets a humanized preview before rendering.

I’m updating `prompt show -f markdown` and `prompt copy`; `show -f raw` and JSON are left byte-exact.

Clipboard copy now writes the paste-safe display form and keeps the fallback pointing to `show -f raw` for the canonical escape hatch.

For the mobile ChangeSpec tag catalog, I’m only humanizing the `project` display field; the tag and ChangeSpec identity fields stay canonical as planned.

I’m changing future ChangeSpec name minting now: canonical project routing stays in the project-file arguments, but generated NAME/branch strings use the configured display prefix.

I’m also humanizing any incoming raw-prefixed base name before suffix reservation, so we don’t mint mixed names like `sase_gh_...`.

The agent-commit ChangeSpec creator now derives the visible NAME from the display project name but still writes it into the canonical project file.

I’m sweeping the ChangeSpec display widgets and notification surfaces next. These are separate from canonical lookup/storage, so I’m using `humanize_cl_name` only at render time.

The display widgets split rendering across helper modules, so I’m opening the list-row formatter and detail body section where NAME/PARENT are appended.

I’m patching the ChangeSpec row and detail renderers now. The Option ids and lookup keys remain the canonical names; only the visible `Text` content changes.

The ChangeSpec detail panel now displays humanized NAME/PARENT and running-claim names, while the hint maps and file paths remain canonical.

I’m applying the same display-only name mapping to the non-TUI Rich ChangeSpec display path.

I’m checking the ChangeSpec clipboard helpers because copy actions are user-facing paste surfaces and can otherwise bypass render-only fixes.

There are also explicit notification list/show renderers. I’m opening those now to humanize notes/action labels without altering stored action data used for navigation.

Notifications often carry names in plain prose rather than VCS tags, so I’m adding a small text helper that rewrites standalone/raw-prefixed name tokens without touching slash paths.

I’m adding focused coverage for the prose helper so it rewrites notification-style phrases while leaving slash paths alone.

I’m humanizing notification notes at render time in CLI list/show, modal rows, and toast previews. Action data in markdown is also display-mapped, but JSON stays canonical.

I’m applying the same notification text helper to the TUI notification list rows.

The notification row patch landed the helper in the middle of the class; I caught that before running tests and I’m moving it to module scope after the class methods.

I’m fixing the misplaced helper so `action_jump_to_entry` keeps its original body intact.

I’m updating toast formatting so notification popups don’t show raw names from notes or action data.

I’m checking clipboard tests before changing ChangeSpec copy behavior; some copy actions may be documented as raw storage escape hatches.

I’m adding tests for the VCS ref prefix round-trip so a displayed `#gh:sase_fix_1` canonicalizes back to `#gh:gh_..._fix_1`, and raw stored refs humanize for display.

The alias service already has fixtures for display names, so I’m adding the prefix behavior tests there.

The new tests cover both exact display-name refs and display-name prefixes used by legacy ChangeSpec names.

I’m checking affected CLI tests so I can update or add focused assertions without fighting existing documented JSON/raw behavior.

I’ve covered the listed confirm modals in wait/relaunch. I’m doing a quick `ConfirmKillModal` sweep now for any other direct `cl_name` descriptions in the same surface class.

The sweep found another kill confirmation path in agent kill and a bgcmd kill confirmation. I’m humanizing the visible labels there too.

The bgcmd confirm path already uses its display project label. I’m patching the agent kill confirm path.

The grep found prompt-panel header paths that still append `agent.cl_name` directly. I’m checking whether they’re identity-only or visible labels, and patching visible labels.

I’m patching the detail headers so ChangeSpec labels go through the same helper while project labels keep using the existing project-display helper.

The standard agent detail header is getting the same visible ChangeSpec-name mapping.

The agent run log modal titles still include raw `cl_name`; I’m mapping those visible titles while keeping lookup filters canonical.

I’m patching the run-log title only; its internal `_cl_name` remains canonical for loading matching artifacts.

I’m updating command input/history labels as user-facing modal text; command history storage and matching stay canonical.

I’m humanizing the command modal’s visible CL context but leaving command history sort keys unchanged.

Command history rows and preview metadata now use display names for the CL segment.

I’m patching direct TUI notification strings that interpolate `cl_name`; these are display messages only, so task keys and mutations still receive canonical names.

I’m patching these visible status/action messages; background task payloads and return strings remain canonical where downstream code may inspect them.

I’m applying the same mapping to base ChangeSpec actions like reword, tag, and mail start notifications.

Base action notifications are now display-mapped; the task submission still uses the canonical `cl_name`.

Sync start notifications now use the visible ChangeSpec name.

Only the toast label changes in sync; provider calls still use canonical names.

Task duplicate warnings now display the mapped name, while queue identity stays canonical.

This is a local warning-only change; no queue API behavior changes.

I’m patching notification navigation “not found” warnings so they display mapped names too.

These warning/toast paths now use `humanize_cl_name` or the agent’s display label.

I’m patching proposal rebase start/failure messages to use display names while keeping workspace/provider calls canonical.

I’m also humanizing parent names in proposal/rebase timestamp display.

I’m patching workspace checkout success messages that show a ChangeSpec name.

The checkout still resolves the canonical revision; only the returned message uses the display form.

I’m checking task completion rendering because background task result messages may surface raw canonical names even if start toasts are mapped.

I’m adding a display pass to task completion toasts and task-queue row labels so raw names from task result messages don’t leak.

I’m making task labels and completion toasts display-safe, without changing task dedup keys.

Task completion messages now pass through the prose-name helper before toast display.

I’m checking agent group/banner rendering because family/group summaries can contain aggregated raw `cl_name` values.

Agent group banners can use raw ChangeSpec group keys, so I’m mapping only the visible banner suffix; group keys stay canonical for folding/navigation.

I’m applying the same visible-label mapping to ChangeSpec group banners.

The ChangeSpec grouping code has a different structure, so I’m opening its render helper directly.

ChangeSpec group banner text now goes through the helper; project/date/status labels are unaffected unless they match a known raw project-prefix token.

I’m checking ChangeSpec grouping keys because project-level banners can be raw project keys if they’re derived from `project_basename`.

Project-group keys now use the display project name for ChangeSpec list banners; `project_basename` remains available on the model and JSON paths.

I’m checking prompt replay/copy tests because `prompt copy` intentionally changed from canonical text to paste-safe display text.

The existing copy test uses text without VCS refs, so the new behavior remains compatible there. I’ll add targeted humanization tests instead of rewriting unrelated assertions.

I’m adding targeted TUI tests for completion, wait/fork tag prefill, and commit labels so the main leaked surfaces are covered.

I’m adding the commit label test next to the existing commit metadata tests.

I’m adding completion test coverage for display tag/snippet and canonical search aliases.

I’m adding a wait/fork VCS tag test that verifies display prefixes are emitted from stored canonical prompts.

I noticed that new test should keep the file’s annotation style, so I’m adding the missing type import and return annotation.

I’m adding prompt markdown/copy tests that distinguish display text from raw/JSON escape hatches.

The prompt tests will patch the display map directly so they don’t depend on project files on disk.

I’m adding a `changespec current` display test so plain/markdown are mapped but JSON remains canonical.

I’m extending the test helper to allow a raw-prefixed parent name, then asserting display vs JSON behavior.

The current command still prints canonical file paths, so I’m keeping the test focused on NAME/PROJECT/PARENT display fields rather than paths.

I’m adding a suffix-reservation test for future ChangeSpec names so the canonical project file is used but the returned NAME has the display prefix.

The new suffix test patches only the display-name helpers used by the function, so existing allocation tests remain independent of the real project catalog.

I’m checking workspace-list tests because the human header changed by removing `key=...` from non-JSON output.

I’m doing another grep pass over direct visible `cl_name`/project labels to catch any high-signal leaks before formatting.

The remaining direct visible `cl_name` hit is the ChangeSpec name copy toast and copied text; I’m mapping that paste surface.

I’m doing a broader scan for direct raw-name formatting after the targeted patches.

I’ve finished the broad implementation pass and am moving into verification now. I’m going to format the touched Python, run the targeted regression tests, then run the repo-required `just check`.

The worktree has the expected set of changes: helper logic, TUI surfaces, CLI/mobile output paths, and focused tests. I’m starting with `just install` because this workspace may have stale editable dependencies.

Install completed cleanly. Next I’m running the repo formatter so the style pass doesn’t obscure functional test failures.

Formatting is clean. I’m running the focused tests that cover the new helper behavior, alias rewriting, display rendering, prompt replay, and ChangeSpec name generation before the full check.

That test command hit the system Python instead of the workspace virtualenv, so dependencies like `rich` and `textual` were missing. I’m rerunning through the workspace interpreter.

The focused suite is mostly passing now. Two issues surfaced: the new completion test used a prompt shape that the existing VCS parser does not classify as a workflow tag, and commit-header expectations now pick up a real display-name mapping from the temp project root. I’m tightening those tests against the intended behavior.

One failure is an implementation bug, not a test issue: I changed the primary commit repo fallback from the project-file stem to the parent directory, which turns `/tmp/test.sase` into `tmp`. I’m restoring the old stem-based behavior and keeping the new display-name mapping on top.

The completion path has a subtler contract: only project workflow tags become the badge, while ChangeSpec-like refs are still included for search. I’m going to adjust that test to use a project tag for the badge and a raw canonical ChangeSpec ref in the body for the search alias.

I’ll patch the implementation fallback first, then update the completion test fixture to exercise both badge humanization and canonical search without fighting the parser.

I’m applying the narrow patch now: commit repo labels will again derive from the `.sase` filename stem, and the completion fixture will isolate the parser behavior while still checking the new humanized display/search behavior.

The implementation fallback is fixed. I’m updating the one completion test so it matches the existing parser contract while keeping the new regression assertions intact.

Those fixes are in. I’m reformatting the touched files and rerunning the same focused suite.

Formatting stayed clean. I’m rerunning the focused tests now.

The focused regression suite is green: 106 tests passed. I’m starting the required `just check` now; this is the full lint/type/test gate for the repo.

`just check` got through formatting and ruff, then mypy found one type issue in a changed notification helper: the callback target is typed as `object`, so mypy no longer accepts `.notify(...)` directly. I’m tightening that code path now.

The issue is only the placement of a `type: ignore` on a multiline `notify` call. I’m making that call simple so mypy sees the existing ignore correctly.

The mypy fix is in. I’m running formatting once more, then I’ll rerun the full check.

Formatting remains clean. I’m rerunning `just check` now.

`just check` has passed the formatter, ruff, mypy, script lint, visual lint, and SASE validation stages. The test stage is still running.

The full test stage is still in progress. I’m waiting for the final result rather than stopping at the partial lint success.

No new output yet; `just check` is still running in the test phase.

The full gate reached the end and found five failures out of 15,505 tests. Three are Rust/Python cleanup parity tests, one is a PNG snapshot, and one is in quick-agent VCS prefix persistence. I’m rerunning the failing tests serially to get complete failure details before changing anything.

The quick-agent failure is from my TUI display change assuming every selection object has `display_name`; that needs a fallback. The Rust parity failures look unrelated to this display-name work and point at the linked core backend, but I’ll inspect enough to decide whether this workspace needs a core update or whether it’s a pre-existing mismatch.

The quick-agent bug is straightforward: I’m changing the lookup to `getattr(..., None)` so lightweight test doubles and older agent shapes still work.

That fallback is patched. I’m rerunning the quick-agent test before looking deeper at the Rust parity failures.

The quick-agent regression is now green. I’m pulling the visual snapshot failure separately so I can inspect exactly what changed.

The visual test is marked out of the default selector, so the direct command deselected it. I’m checking the repo’s `just test` invocation and visual markers so I can rerun that PNG test the same way the full gate does.

I found the selector: visual tests need `-m visual` to override the default marker expression. I’m running just the failing PNG with that marker now.

The PNG failure is a real snapshot diff at 1.29%, so I’m inspecting the generated expected/actual/diff artifacts before deciding whether the snapshot should be accepted or whether the UI text changed unintentionally.

The visual diff is from an intentional user-facing detail change: the ChangeSpec detail panel now shows the parent using the display-safe name, which shifts the card height. I’m checking the approved plan wording once, then I’ll update that specific PNG golden if it matches the plan.

The approved plan explicitly calls out ChangeSpecs-tab row/detail `NAME/PARENT` display cleanup and says to regenerate PNG goldens where a raw key legitimately became a display name. This snapshot change is in that bucket, so I’m updating only the affected golden.

The affected PNG golden was updated and the visual test passes with update mode. I’m checking the linked `sase-core` workspace now because the remaining full-check failures are Rust-core/Python cleanup parity, outside the display-name plan but blocking the required gate.

The linked core workspace was stale; `sase workspace open` cleaned and updated it to `origin/master`. I’m rebuilding the local editable install so the Python package uses the refreshed Rust extension, then I’ll rerun the parity failures.

`just install` is recompiling the refreshed Rust core now, so this run will take longer than the earlier no-op build.

The Rust extension build has moved into the Python binding crate. Waiting for install completion.

The refreshed core installed as `sase-core-rs 0.3.3`. I’m rerunning the prior failing tests now.

The previous blockers are resolved: the cleanup parity tests pass after refreshing core, the quick-agent test passes, and the updated PNG golden passes. I’m running the required full `just check` again from the top.

The rerun has passed all lint/type/validation stages again and is in the full test stage.

No test output yet; the full suite is still running.

The test phase is still running. I’m continuing to wait for the final result.

`just check` passed, including the full test suite. I’m doing a final worktree/diff sanity pass now so the close-out accurately describes what changed.

The worktree only shows intended source/test/PNG changes in the main repo; no memory files were modified. I’m checking the linked core status too, since I had to refresh it for the test gate.

Implementation and verification are complete. I’m doing one last targeted code review over the shared helpers and the highest-risk display/prefill paths before finalizing.

One final review caught a real edge case: quick-launch from a non-project agent must use the CL/ref name, not `agent.display_name`, because workflow root display names can be workflow labels. I’m tightening that before rerunning the checks.

That edge case is patched. I’m checking the existing quick-launch tests and adding a focused regression if there isn’t already one for workflow display labels.

There wasn’t a regression for that workflow-label case, so I’m adding one to keep the VCS ref tied to the CL name.

The regression test is in. I’m formatting and then rerunning the quick-launch file plus the earlier focused suite before the final full check.

Formatting remains clean. I’m running the focused test set, including the new quick-launch regression.

The new quick-launch test failed because it expected the selection to be saved, but the fixture project name is intentionally not launchable under the modal discovery guard. The behavior under test is the prompt prefix/display, so I’m changing the assertion to focus on that.

Actually I can keep the save assertions by making this fixture launchable through the same discovery guard used by the persistence helper. I’m adding that monkeypatch so the test exercises the full quick-launch path.

The launchability guard is patched in the regression test. I’m rerunning the focused suite.

The new quick-launch regression passes. I’m rerunning the broader focused suite now.

The focused suite is green again: 111 tests passed. I’m running the final required `just check` one more time after the last patch.

Final `just check` has passed lint/type/validation and is in the full test stage.

The full test stage is still running.

No new output yet; still waiting on the full suite.

Final `just check` passed, including the full test suite. I’m doing the final status snapshot now.

Implemented the approved raw-project-key eradication plan.

Key points:
- Added shared `humanize_cl_name` / text helpers and prefix-aware VCS alias rewriting.
- Updated TUI display, prompt prefill, clipboard, notifications, modals, CLI, prompt history/search/show/copy, mobile catalog, and ChangeSpec display/name generation paths.
- Kept storage, identity, JSON, raw prompt output, and file paths canonical.
- Updated the affected ACE PNG snapshot for the intentional ChangeSpec detail display change.
- Refreshed/rebuilt the linked `sase-core` extension to clear stale parity-test failures; no linked-core files were modified.

Verification:
- `just install`
- Focused regression suite: `111 passed`
- Required full gate: `just check` passed.

I made the listed changes in this session, so I’m going to use the required `sase_git_commit` workflow and commit exactly those files.

The commit skill is logged. I’m checking the final diff and status now so the commit message describes only this change set and the file list matches the finalizer.

The status and diff match the implementation files and tests from the completed plan. I’m writing a focused commit message now, then I’ll stage exactly the finalizer-listed files through `sase_git_commit`.

The commit message is in place. I’m invoking the SASE commit wrapper now with one `-f` per changed source, test, and snapshot file.

The SASE commit wrapper completed successfully. I’m checking branch status now to confirm the working tree is clean and the commit is not left only locally.

The repo is clean and synced with `origin/master`. I’m grabbing the final commit id for the close-out.

Committed the implementation with the required SASE commit workflow.

Commit: `4cce6a46b fix: humanize project-prefixed ChangeSpec names`

Status after commit: clean and synced with `origin/master`. Prior verification completed successfully with `just check` passing.
