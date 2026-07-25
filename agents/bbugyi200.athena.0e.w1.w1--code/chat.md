# Chat History - ace-run

- **TIMESTAMP:** 2026-07-07 12:57:13 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** 0e.w1.w1--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-0e_w1_w1__plan-260707_114801.md`
- **2. --code** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260707_114801.md`

## Prompt

%model:@codex_coder
#gh:gh_sase-org__sase @sdd/tales/202607/pr_terminology_rename.md

The above plan has been reviewed and approved. Implement it now.


## Response

I’ll read the approved plan first, then map it onto the current code so the implementation matches what was reviewed. After edits, I’ll run the repo’s required checks.

The plan is broad and touches linked repos, so I’m going to first inventory the current symbol/text surface and open the numbered linked workspaces using the required SASE command. I’ll keep memory files out of scope unless you explicitly approve them.

The linked workspaces are open at the matching workspace number. The initial scan confirms most of the noisy matches are historical `sdd/` material, so I’m narrowing to active code, docs, tests, schemas, and generated prompt sources before editing.

The active surface separates into two categories: review URL fields (`cl`, `cl_or_pr`, `cl_url`) and long-standing `cl_name` identifiers that usually mean ChangeSpec/branch names. I’m going to prioritize the reviewed API/wire rename and writer normalization, then adjust visible text without doing unsafe blind `cl_name` churn.

Because this touches generated skill prompts, I’m using the `sase_memory_read` skill to review the required generated-skills memory before editing those sources.

The generated-skill note confirms edits belong in `src/sase/xprompts/skills/`, followed by regeneration, not direct edits to installed skill files. I’m reading the model/parser/writer files now.

I’ve found the concrete review URL model names: Python `ChangeSpec.cl`, Rust wire `cl_or_pr`, and GitHub `changespec.cl`. The compatibility parser already accepts both labels, but writers still preserve or emit `CL`, so I’m adding shared PR label helpers and moving the review URL API over to `pr_url`.

I’m making the model rename with a compatibility alias: new code will use `pr_url`, and old `.cl` reads/writes still work during the rollout. That lets the parser/wire/plugin changes land together without forcing unsafe `cl_name` renames that actually refer to branch or ChangeSpec names.

Next I’m updating the wire contract to schema version 3. The deserializers will accept both the new `pr_url` key and the old `cl_or_pr` key so older parser output and serialized fixtures remain readable while new output uses `pr_url`.

I’m going to apply the first code changes now: add a shared review-field helper, rename the Python model/wire/parser review URL field, and normalize ChangeSpec writers to emit `PR:`. After that I’ll do the Rust core schema rename and then update callers/tests.

I’m updating the primary repo first. This includes compatibility helpers, parser/model/wire conversion, and writer functions; then I’ll run targeted searches to catch callers still reading `.cl` or emitting `CL:`.

The primary model and writer helper are in place. I’m doing a quick syntax/read pass before cascading the mechanical caller updates, because field header tuples and dataclass init changes are easy places to introduce small errors.

The syntax check passed. I’m now changing creation paths so new ChangeSpecs always write `PR:`, while still accepting legacy `cl_url`/`cl_label` keyword callers during the rollout.

One patch hunk didn’t apply cleanly, so I’m splitting those caller updates into smaller patches with tighter context.

I’m doing the mechanical review URL caller rename now: `.cl` becomes `.pr_url`, and wire fixture keys move from `cl_or_pr` to `pr_url`. This is scoped to code/tests, not `sdd` or memory.

The direct `.cl` and `cl_or_pr` usages are rewritten. I’m scanning `cl_url` next so I only rename API parameters that represent the review URL and avoid unrelated fixture keys.

The `cl_url` scan is mostly review URL API names, including pluggy hook parameter names. I’m doing a scoped bulk rename to `pr_url`; the functions already have legacy keyword compatibility where needed.

The bulk rename intentionally exposed the legacy keyword shim as duplicate parameters. I’m correcting those shims to use `**legacy_kwargs` so old `cl_url` callers still work without keeping old names in the public signature.

The shims are corrected. I’m rerunning a compile pass over the touched Python modules before moving to Rust/core tests.

I’m switching to the Rust core now: schema version bump, `ChangeSpecWire.pr_url`, parser internals renamed from `cl`, and serde alias support for legacy `cl_or_pr` input.

The core-wide `cl_or_pr` token is now `pr_url`. I’m applying the manual Rust edits for compatibility aliases and parser state names.

The Rust field alias is in place. I’m updating schema-version literals and adding a focused compatibility test for old `cl_or_pr` dicts.

Only ChangeSpec wire tests need the version bump; mobile fixtures also have version 2 but are unrelated, so I’m leaving those alone.

The schema literals are bumped. I’m reading the updated Rust wire tests now to catch any macro or fixture issue before formatting.

The core scan is clean except for the intentional serde alias. I noticed one test now references the schema constant without importing it, so I’m patching that and adding the explicit legacy-key round-trip test.

I’m patching the missing import and a small serde regression test, then I’ll run `cargo fmt --check` once the linked GitHub plugin is updated.

The Rust core compatibility patch is done. I’m returning to the primary repo to clean up remaining writer/update helpers, tests, and hook signatures after the bulk rename.

The primary snapshots still show the old schema number, so I’m updating those and the tests that assumed writers could still emit `CL:`. New behavior will keep reading `CL:` but rewrite/write `PR:`.

I’m updating the focused status field tests to assert the compatibility behavior directly: legacy `CL:` input is accepted, touched lines become `PR:`, and new fields insert as `PR:`.

The status-field tests now match the new writer behavior. I’m sweeping remaining active `CL:` assertions and display-label usage next, keeping legacy `CL:` input where it proves backward compatibility.

I’m replacing display-time label lookup with the canonical `PR:` label. Provider-specific labels are no longer used for writing or showing the review URL.

That patch missed some file context, so I’m reading the exact import/header sections and will apply a tighter patch.

I have the exact contexts now; applying the display-label cleanup.

Display code now uses `PR:` directly. I’m cleaning tests that patched `get_change_label`, since creation no longer asks providers which label to write.

Those tests only patched label lookup to control old `CL`/`PR` output. I’m removing those patch entries and updating the one explicit clipboard expectation to `PR:`.

Now I’m updating the clipboard test and the remaining assertions around newly-written `PR:` lines.

The clipboard test now follows the new label. I’m checking the ChangeSpec add test around its parent insertion assertion before changing expected text.

Those remaining `CL:` literals are legacy parent fixtures, which are useful compatibility coverage. I’m scanning again for actual expected-output `CL:` assertions.

There are no runtime callers left for `get_change_label`; it remains as a compatibility hook. I’m moving on to linked GitHub plugin code so pluggy hook signatures match the renamed `pr_url` parameter.

In the GitHub plugin, the review URL is a PR URL, so I’m renaming hook parameters and recorded-PR reads to `pr_url`, while leaving the broader `vcs_get_cl_number` hook alone because that is a separate VCS-provider API still present in the primary repo.

The GitHub plugin scan is clean for the targeted CL terminology. I’m applying the Telegram docstring update next.

I’m adding PR-named status update functions now, keeping old `*_cl` aliases for compatibility. Then I’ll update production callers to the PR names.

The remaining old function names are limited, so I’m introducing PR-named functions and converting the production imports. Tests can keep legacy alias checks where useful.

Production callers now use PR-named reset/update functions. I’m updating tests that patched the old imported name in `sase.ace.revert`.

I’m checking the status package exports and a compile subset to catch any import mistakes from the rename.

The remaining old names in primary code are now mostly compatibility aliases or broad `cl_name` branch/ChangeSpec identifiers. I’m checking active filenames/imports next, then I’ll do a user-facing text pass over docs, xprompts, and tests.

The old `get_change_label` patches are gone from the focused workflow tests. I’m running a tighter scan for stale expected kwargs and schema text before targeted tests.

I’m renaming the submitted-check script to PR terminology while keeping the old console entry as a compatibility alias.

The new PR-named console script is added and the old one remains as an alias. I’m checking references before moving on.

The remaining scan is mostly documentation, comments, xprompt text, and long-standing `cl_name` branch/ChangeSpec identifiers. I’m doing a controlled text pass for visible terminology (`CL/PR`, `CL URL`, `CL field`, `CL number`, and generated xprompts) without renaming `cl_name` variables that mean ChangeSpec names.

That pass handled the mixed `CL/PR` phrases. I’m checking the remaining active documentation and prompt text for uppercase `CL` to update the obvious product terminology and leave explicit legacy `CL:` compatibility references only where intentional.

The remaining docs are mostly straightforward product terminology. I’m doing a broad uppercase `CL` to `PR` pass over active docs and bundled xprompts, then I’ll restore the few intentional legacy `CL:` compatibility mentions.

The broad pass is complete. I’m correcting the intentional compatibility text so docs say new files use `PR:` while legacy `CL:` remains readable.

The broad replacement created a few duplicate `PR / PR` phrases. I’m fixing the ChangeSpec docs and skill implementation notes by hand.

Only the intended legacy `CL:` compatibility mentions remain, plus two duplicate `PR / PR` phrases in project docs; I’m fixing those now.

The docs compatibility wording is corrected. I’m scanning active source for remaining visible `CL` strings now.

I’m picking up from the implemented rename work and checking the current diffs/scans before running the required validation. The main risks now are leftover user-facing `CL` terminology, generated skill sync, and formatting/test fallout across the linked repos.

The diff is broad but contained to the expected repos. I’m going back to the approved tale now so I can reconcile the implementation against its exact checklist before I validate.

The approved plan matches the implemented direction: schema bump, dual-read compatibility, writers normalize to `PR:`, and linked plugins use PR-oriented APIs. I’m doing a focused residual scan now, excluding protected historical logs, so I can fix only the current-behavior wording and compatibility gaps.

The first scan was too broad because it caught unrelated identifiers that happen to contain `cl` patterns. I’m narrowing it to exact old review-field terms and obvious renamed APIs, then I’ll separately look at known module/file names like `cl_handler.py` and `rename_cl_modal.py`.

There is one larger issue left than the review URL rename: `cl_name` is still the primary internal name for ChangeSpec/branch identity in agent metadata, history, notifications, and core wire records. That is exactly the “not actually PR identifiers” case from the plan, so I’m inspecting the model boundaries before doing a mechanical rename with compatibility aliases.

I’m going to separate two categories now: review URL terms (`CL:`/`cl_or_pr`/`cl_url`) are part of this rollout and need strong compatibility; `cl_name` is an older persisted agent identity key that would require a migration path. I’ll clean the visible docs/comments/UI for that second category and keep compatibility keys where changing them would break existing agent metadata.

Most remaining uppercase `CL` occurrences are visible wording or comments, not parser compatibility. I’m about to do a targeted text cleanup: `CL:` compatibility stays in parser/tests, but UI/docs/messages for ChangeSpec names become `ChangeSpec`, and review-number/URL wording becomes `PR`.

I found a concrete behavioral gap in commit/renumber helpers: a few section scanners still stop only on `CL:` and would misparse newer `PR:` files. I’m fixing those with the same review-field helper before doing the surface-wording cleanup.

I’m editing the section scanners now so `PR:` is treated as the review-field boundary everywhere `CL:` used to be. This avoids subtle corruption in commit/proposal helpers when a ChangeSpec has already been normalized.

The commit helper boundary checks are now using the shared review-field prefixes, so both `PR:` and legacy `CL:` are recognized consistently. I’m checking the remaining exact `CL:` uses to make sure they are compatibility tests or visible labels that still need changing.

The exact `CL:` matches are now mostly tests/fixtures and a few visible TUI context labels. I’m changing current fixtures to `PR:` while leaving dedicated legacy-`CL:` compatibility cases in place.

I’m keeping command IDs like `copy.changespecs.cl_number` for compatibility unless the implementation already has a clean alias point; the visible label now says “PR number.” The next edits are mostly docstrings/messages and a few CLI/TUI context labels.

Three active module filenames still carry old terminology: `cl_status.py`, `rename_cl_modal.py`, and `main/cl_handler.py`. I’m renaming those modules and their internal class/docstring names, then updating imports/tests to use the new names.

I’m applying the file renames with compatibility-neutral naming: `pr_status` for review status checks, `rename_changespec_modal` for the TUI modal, and `commit_handler` for the commit/restore/revert CLI handlers.

The files are renamed; I’m updating the imports and tests now so the repo no longer depends on the old module names.

I’m also renaming the matching test module so the test suite reflects the new status module name.

The module rename scan is clean. I’m patching the remaining visible messages in revert/archive/agent dialogs from `CL` to `PR` or `ChangeSpec` based on what the value actually represents.

The lifecycle messages now talk about PR fields and ChangeSpec branches instead of CLs. I’m cleaning the small TUI labels that displayed `CL:` for agent context.

The visible context label now says `ChangeSpec`. I’m applying the same correction in the kill/relaunch confirmation dialogs.

`get_change_label` is now compatibility-only: writers no longer ask providers whether to emit `CL` or `PR`. I’m making its docs return `PR`-oriented wording and leaving the hook in place for old plugins instead of ripping it out mid-rollout.

I’m correcting the remaining active comments/messages around submission and suffix allocation so they refer to PR branches or ChangeSpec names instead of CLs.

The submission hook kill message is now ChangeSpec-based. I’m patching suffix-allocation wording next; the code path still has legacy function names for compatibility, but new comments/output should be accurate.

The commit workflow comments now use ChangeSpec/branch terminology. I’m tightening the parent auto-detect warning and suffix rename logging in the same pass.

Suffix rename logs now refer to branches. I’m replacing remaining current-status examples and labels that still say `CL` where they should say `PR` or `ChangeSpec`.

The remaining visible runner output labels are ChangeSpec names, not PR URLs, so I’m changing those prints to `ChangeSpec:`.

A few scheduler constants still include `cl_submitted`; those are internal check-type names and might be persisted. I’m first fixing visible log/doc wording while preserving the internal key unless there is a simple alias path.

Error reports now label that field as `ChangeSpec`. I’m updating the check-cycle descriptions next without renaming persisted check-type IDs yet.

Current check-cycle logs now say PR. I’m doing another exact uppercase scan so the next fixes are driven by remaining matches instead of broad replacement.

The remaining scan still caught `ACLs` as a false positive because of a loose `CLs` pattern. I’m fixing the real core README/parser comments now and then I’ll narrow the scan to word-boundary matches.

Core documentation now describes `PR` as canonical and `CL` as legacy input. I’m rerunning with word-boundary matching so unrelated `ACLs` are ignored.

There are still many comment/docstring-only `CLs tab` and `CL name` occurrences. I’m doing a phrase-based cleanup that avoids identifiers and legacy `CL:` compatibility code.

The first bulk command only hit directory arguments and made no changes. I’m rerunning it over the file list from `rg --files`.

The phrase cleanup completed. I’m scanning again and checking for accidental wording around legacy compatibility before moving into formatting/tests.

The cleanup surfaced a few accidental `PR rows` phrases in docs; those should be `ChangeSpec rows`. I’ll fix those, then address the remaining active-source messages and leave only compatibility hook names and legacy parser references.

I’m checking the copy-mode keymap now. If there is a clean way to accept both `cl_number` and `pr_number`, I’ll move the default to `pr_number` without breaking old configs.

The VCS provider still exposes `get_cl_number`, which is a compatibility API. I’m adding PR-named aliases and updating current callers/UI to use `pr_number`, while leaving the old hook names callable for existing plugins.

I’m switching the built-in copy key from `cl_number` to `pr_number` and adding fallback lookups so old user configs that still contain `cl_number` keep working.

The copy action now uses `_copy_pr_number` and the visible name-copy notification says ChangeSpec. I’m updating the footer/help rendering to read either `pr_number` or old `cl_number`.

The footer has a compatibility fallback for old keymaps. I’m applying the same pattern in the help modal.

The help modal still had old row text and the old key name. I’m patching that file directly.

The help modal now resolves both old and new copy key names. I’m updating command availability to gate both `copy.changespecs.pr_number` and the legacy ID.

The remaining `cl_number` source matches are now compatibility paths plus VCS hook names. I’m adding PR-named provider methods and keeping the old names as aliases, then updating GitHub/bare-git plugins to implement the new hook.

The base provider now has `get_pr_number` with `get_cl_number` as a compatibility alias. I’m adding the same pattern to the pluggy manager and hook spec.

The hook spec and manager now prefer `vcs_get_pr_number` and fall back to legacy `vcs_get_cl_number`. I’m updating bundled plugins.

I’m applying the VCS hook alias in the GitHub plugin too, so it advertises the PR-named hook while retaining the old hook for compatibility.

The GitHub plugin now implements `vcs_get_pr_number`. I’m updating its docs/tests to use the PR-named method while keeping the old method available.

That mechanical rename may have touched the compatibility alias name, so I’m checking the GitHub plugin and restoring the legacy alias if needed.

The mechanical rename did duplicate `vcs_get_pr_number`; I’m restoring the second method as the legacy `vcs_get_cl_number` alias.

Primary code no longer needs current callers for `get_cl_number`, but the provider docs/tests still mention it. I’m moving docs to `get_pr_number` and leaving legacy API tests only where they explicitly cover compatibility.

The provider docs/tests now use `get_pr_number`; the old hook remains in source only as a compatibility fallback. I’m checking those references now.

The only `cl_number` in current behavior now is compatibility fallback code plus a few test names. I’m updating the command availability tests to the new command ID.

Command availability now references `copy.changespecs.pr_number`. I’m doing a source-only scan next, since many remaining test strings are synthetic names and less risky.

The remaining source matches are mostly comments/docstrings, plus a handful of visible notifications/modal titles. I’m applying a focused source cleanup for those now.

The source phrase cleanup finished. I’m scanning active source again for actual remaining matches and then I’ll inspect any suspicious replacements.

The active source scan is now down to legacy compatibility references plus a few missed comments/help strings. I’m cleaning those missed comments and leaving the compatibility identifiers intentionally.

Those remaining comments are cleaned up. I’m running one more active-source scan to confirm the only source matches are explicit compatibility hooks/constants/tests.

The active-source matches are now almost entirely compatibility names. I’m fixing the two stale examples/comments that are not compatibility.

I’m converting current test fixtures to `PR:` now. Dedicated legacy `CL:` compatibility tests stay in `test_status_state_machine_field_updates` and parser/wire compatibility tests.

Current fixtures now use `PR:`. I’m checking the tests that assert old user-facing messages so they line up with the new wording.

I found three test assertions still expecting old messages. I’m updating them to the new strings.

The old message assertions are updated. I’m doing a broader test scan now, but I’ll treat synthetic names like `CL-1` as low-risk unless they are rendered text expectations.

The primary active-source scan is down to explicit compatibility hooks/constants. I’m checking linked repos now for any non-compatibility leftovers before formatting.

Linked repo scans are clean apart from explicit legacy aliases and parser compatibility. Since `src/sase/xprompts/skills` changed, I’m syncing generated skills now as required by the generated-skills memory instructions.

Skill generation found no file changes. I’m running the follow-up `chezmoi apply` step from the generated-skills workflow so the managed skill locations stay in sync.

Generated skill sync and chezmoi apply both completed without visible output changes. I’m checking git status across the repos before formatting.

The status is broad because the terminology sweep touched docs, xprompts, comments, and tests. I’m running diff checks and formatters next; that should catch syntax/line-length fallout from the scripted replacements.

Whitespace checks are clean. I’m starting the required validation sequence now, beginning with installing the primary repo environment before formatting/checking it.

`just install` is building the local Rust binding from the linked `sase-core` workspace; it is still running.

Primary install completed. I’m running the repo formatter now so line wrapping/import ordering from the rename gets normalized before checks.

Primary formatting completed; ruff fixed imports/formatting and Markdown prettier ran with no memory-file changes. I’m formatting the Rust core next.

Rust formatting is clean. I’m formatting the GitHub and Telegram plugin repos now.

Formatting is done across the Python plugin repos. I’m starting the core validation now: `cargo fmt --check` followed by the Rust workspace tests.

`cargo fmt --check` passed. I’m running the core test suite now.

Core validation passed: `cargo fmt --all --check` and `cargo test --workspace`. I’m running the required primary `just check` now.

`just check` got through ruff/mypy and failed only on pyvision: the private `_apply_cl_update` alias is not allowed. I’m removing that private alias and updating tests to call `_apply_pr_url_update` directly; public compatibility functions stay.

The private alias is gone and tests now use the PR-named helper. I’m reformatting the small change and rerunning `just check`.

Formatting remained clean. I’m rerunning the primary `just check`.

`just check` now passes lint/pyvision and fails only on SASE initialization validation: generated provider skill files need overwrite. I’m running the indicated `sase init skills` step.

` sase init skills` reported no writes, but validation still requested overwrites. I’m checking the command options and then I’ll run the forced form if available.

The forced option is available. I’m running `sase init skills --force`; this is the validation-required generated-skill deployment step.

The system `sase` binary still reports no writes; validation uses `.venv/bin/sase`, so I’m running the forced init through the workspace venv binary.

The workspace venv `sase init skills --force` wrote 10 generated skill files, committed/pushed the chezmoi update, and applied it. I’m rerunning primary `just check`.

`just check` is past all lint and SASE validation now; the test phase is still running.

The primary test suite is still running without new output yet.

Still waiting on `just check`; no failures have printed so far.

The primary suite is still in progress. I’m continuing to wait for completion rather than interrupting it.

I’m picking up from the running validation. First I’m going to collect the `just check` result, then I’ll handle any failures before moving on to the linked repo checks.

That validation process is no longer attached, so I can’t trust its final status. I’ll re-run the required checks after a quick status/read scan so any remaining failures are concrete.

The working trees are in the expected edited state across the primary repo and three linked repos. I’m re-running the primary repo’s required `just check` now, since the previous session result was lost.

The primary check is past formatting, linting, pyvision, and SASE validation. The remaining work is the test suite, which is still running.

No failures have surfaced yet; the test phase is still quiet, so I’m letting it continue rather than interrupting it.

The check is still running in the test suite. I’m continuing to poll for the actual exit status so we don’t miss a late failure.

Still no output from the test runner. This repo’s full check can be slow after broad UI text changes, so I’m waiting for completion before touching the linked repos.

Primary `just check` found seven test failures. They’re concentrated in renamed messaging, wire goldens, and visual/onboarding snapshots, so I’m going to rerun those specific tests with full output and patch the expectations or snapshots where the new wording is intentional.

The direct `pytest` command hit the system environment, which lacks the visual test dependency. I’m switching to the repo virtualenv so the failure details match `just check`.

The non-visual failures are straightforward: two assertions still expect `CL/PR`, and the golden snapshots need to reflect the current no-review-url wire value. I’ll patch those expectations first, then handle the two PNG snapshot diffs separately.

I’m making these test expectation edits now. For the wire goldens, I’m preserving the existing empty-string behavior for absent review URLs rather than changing runtime semantics during a terminology rename.

The text/golden expectations are patched. Next I’m checking how the visual suite is gated so I can update only the intentional PNG snapshots for the changed onboarding/tab-guide copy.

The visual tests are included through the project’s `tools/run_pytest` wrapper, and snapshot updates use `--sase-update-visual-snapshots`. Since the only visual diffs are expected wording changes, I’ll update those two goldens through the existing visual test mechanism.

Those visual tests failed before snapshot comparison because their guard strings still used `CL/PR`. I’ll update the guards, then rerun the snapshot update.

I found the new guard strings in the implementation: the tab guide now says `One ChangeSpec = one PR`, and onboarding starts with `Every PR...`. I’m aligning the visual tests to those strings.

The visual test guards are updated. I’m rerunning those two visual cases with snapshot update enabled to accept the intentional rendered-text changes.

The two PNG goldens have been regenerated and the targeted visual cases now pass. I’m rerunning the original failing set to verify the text and wire fixes before kicking off the full check again.

The original non-visual failures are now green. I’m running the full primary `just check` again to catch any failures outside that focused set.

The primary check is through linting and validation again; tests are underway.

The test suite is still running without new output. I’ll keep polling until we have the final exit status.

Still waiting on the full test suite. No failures have printed after the earlier targeted fixes.

The primary `just check` remains in the quiet test phase. I’m continuing to wait for the final result rather than starting overlapping checks.

Primary `just check` is now passing. I’m moving to the linked plugin repos and will run their required install/check lanes so the cross-repo API changes are verified against their own test suites.

The GitHub plugin repo has no local `AGENTS.md`; Telegram and core do. I’m reading those local instructions before running further checks there.

Telegram’s instructions match the expected `just install`/`just check` flow. GitHub’s runner supports `SASE_CORE_PATH`, but the API change is in the installed SASE package too, so I’m quickly checking its project metadata before installing.

Both plugin repos declare `sase` as a package dependency, so a plain install may resolve whatever is already in the venv. I’m checking the tests and installed package state so the linked checks actually exercise the local SASE API where it matters.

Both linked plugin venvs already resolve `sase` to the local primary workspace, which is what we want. I’m running their `just install` steps now, then I’ll run each `just check`.

`just install` in `sase-github` upgraded `sase` to the published package because the local repo’s version metadata is below the plugin’s declared minimum. I’m reinstalling the local core binding and local SASE package into both plugin venvs with dependencies left intact, so their checks run against this change set.

Both local reinstall commands are building or installing the Rust binding. I’m waiting for them to finish before running plugin checks.

The plugin venvs now point at the local SASE and local Rust binding. I’m running `just check` in `sase-github` and `sase-telegram` in parallel.

Both plugin checks passed. I’m rerunning the Rust core format/test checks once more so the final validation set reflects the current cross-repo state.

Core format and test checks are green. I’m doing final hygiene now: whitespace checks, status summaries, and scans for leftover `CL` terminology so I can separate intentional compatibility/internal API references from missed user-facing text.

Whitespace checks are clean in all four repos. I’m running the terminology scans next; if they show only compatibility aliases or synthetic test data, I’ll leave them alone.

The active-source scan now shows only documented legacy `CL:` parsing, `cl_or_pr` wire fallback, compatibility kwargs/aliases, and internal reviewer hook parameter names. I’m checking the approved plan text once before deciding whether those reviewer parameter names are in scope.

The approved plan does call out `cl_number -> pr_number`. The remaining reviewer hook parameter names are internal API surface, so I’m going to rename those to `pr_number` while keeping hook behavior unchanged.

There are no in-repo implementations of `vcs_find_reviewers`, so this is just the abstract/plugin-manager surface. I’m renaming that parameter to `pr_number` to match the plan and avoid leaving misleading `cl_number` identifiers outside explicit compatibility aliases.

That last internal parameter cleanup touched primary source, so I’ll rerun the primary required `just check` after a quick scan to confirm the remaining matches are only explicit compatibility paths.

Formatting made no additional changes. The only scan hits are now legacy compatibility hooks/fields and fallback config keys, so I’m rerunning the full primary check after the parameter rename.

The primary check is through linting and validation again; tests are running for the final pass.

No test output yet, so the final primary test pass is still in progress.

Still waiting on the final primary test pass; no new failures have appeared.

The final primary `just check` passed. I’m doing one last status and scan pass, including `sdd/` markdown, so I can report exactly what remains and avoid accidentally leaving a user-facing `CL` mention behind.

The active repos are clean on whitespace and checks. The remaining broad `sdd/` hits are historical plans/research/event logs, including the approved rename plan itself and bead history; I’m not rewriting those historical records without a narrower instruction.

The generated skill regeneration left the chezmoi working tree clean; its current HEAD is not the commit ID from the earlier summary, so I’m checking the branch/log state before I report that detail.

There’s one active `CL:` literal in deltas persistence that may be a stale field-order list rather than a compatibility helper. I’m checking that file before finalizing.

That `CL:` literal is just legacy section ordering for DELTAS insertion, but the plan asked for central compatibility handling. I’m switching it to the shared review-prefix helper so the compatibility knowledge stays in one place.

That small cleanup touched primary code, so I’m running the primary check one last time. This should be a fast revalidation of the same suite.

The final primary check is back in the test phase after passing format/lint/validation.

No output yet from the final test phase; I’m continuing to wait for the exit status.

The suite is still running quietly. No failures have surfaced after the DELTAS helper cleanup.

Primary `just check` passed after the final cleanup. I’m taking the last scan/status snapshot now.

The final scans are down to explicit legacy compatibility paths in active source/docs, plus one GitHub legacy hook alias; Telegram has no matches. I’m collecting concise diff stats now for the final summary.

Implemented the PR terminology rename across `sase`, `sase-core`, `sase-github`, and `sase-telegram`.

Key points:
- New ChangeSpecs write `PR:` and use `pr_url`; legacy `CL:` and `cl_or_pr` still read during compatibility.
- Bumped ChangeSpec wire schema to v3 with compatibility aliases.
- Renamed active modules/APIs from CL-oriented names to PR/ChangeSpec-oriented names where appropriate.
- Updated TUI text, docs, xprompts, generated skills, tests, and PNG visual snapshots.
- Added/kept compatibility aliases for old `cl_url`, `cl_number`, `vcs_get_cl_number`, and `ChangeSpec.cl` paths where needed.

Validation passed:
- Primary `sase`: `just install`, `just check`
- `sase-core`: `cargo fmt --all --check`, `cargo test --workspace`
- `sase-github`: `just install`, `just check`
- `sase-telegram`: `just install`, `just check`
- `git diff --check` clean in all four repos

Final scans show remaining active `CL` matches only in explicit legacy compatibility code/docs. Historical `sdd/` plans/research/bead/event logs still contain old terminology; I left those historical records untouched. Generated skills were regenerated/deployed through chezmoi, and that tree is clean.

I’ll handle the finalizer now. Since these changes were made during this implementation pass, I’m using the required `sase_git_commit` workflow for the primary repo and each linked repo, then I’ll verify each working tree is clean.

I’ve recorded the skill usage. Next I’m checking each repo’s status and diff summary before committing so the commits only describe the actual changes in each working tree.

The diffs line up with the approved rename: primary repo has the broad ChangeSpec review-field and UI/doc/test sweep, core has the v3 wire/parser rename, GitHub has hook/API terminology updates, and Telegram has a one-line formatting wording change. I’m going to commit each repo intentionally as a whole-repository commit because the changed-file sets are exactly the implementation surface from this pass.

I’m committing the primary repo first with a single feature commit for the terminology rollout. I’m intentionally omitting `-f` here so the wrapper stages the whole repo change set, including renames, deleted old modules, generated snapshots, and new compatibility helpers.

The primary commit hit a merge conflict while syncing with `origin/master`. I’m checking the repository state now; if there’s an in-progress rebase/merge I’ll resolve the conflict in place, continue it, and then resume or retry the SASE commit path as appropriate.

The failed commit attempt staged the intended changes but also let the precommit formatter touch the approved tale file, which was not part of the implementation commit. I’m inspecting that diff and will drop it before retrying so the commit stays scoped.

There isn’t an active merge or rebase, so the wrapper failed before leaving conflict markers. The branch is behind `origin/master`; I’m going to fast-forward/rebase with autostash, resolve any replay conflicts if they appear, then rerun `sase_git_commit`.

The primary repo fast-forwarded cleanly and reapplied the implementation changes. Because that pulled in new upstream code under the same working tree, I’m checking the resulting status and will revalidate before finalizing the commit.

The fast-forward produced no whitespace issues. I’m rerunning the primary required `just check` against the rebased tree before retrying the commit.

The rebased tree exposed one formatting drift in `src/sase/core/wire.py`. I’ll format that file, then rerun the full primary check.

Formatting is corrected. I’m running `just check` again; this pass needs to get through lint, SASE validation, and the full test suite on the fast-forwarded base.

The primary check has cleared formatting, linting, and SASE validation. The test phase is running now.

No failures have surfaced yet; I’m still waiting on the primary test suite to finish.

The test runner is still quiet, so I’m continuing to poll for the final exit status instead of interrupting it.

The primary `just check` passed on the rebased tree. I’m retrying the SASE commit now, again staging the whole intended repo change set.

The primary commit is complete and the primary working tree is clean. I’m moving to `sase-core` next; it is behind its upstream, so I’ll fast-forward with autostash, revalidate core, then commit its whole terminology change set.

`SASE-core` fast-forwarded cleanly and reapplied the changes. I’m rerunning its format and test checks before committing.

Whitespace is clean in core. I’m running `cargo fmt --all --check` and the workspace tests now.

Core validation passed. I’m committing the core wire/parser schema rename now as one repo-scoped change.

Core is committed and clean. I’m checking the two plugin repos next; their working trees are small, so I’ll rerun their `just check` lanes before committing.

Both plugin checks passed. I’m committing `sase-github` first, then I’ll verify the repo is clean before committing Telegram.

The GitHub plugin commit hit the same sync guard. I’m checking whether the remote moved during validation; if so I’ll fast-forward with autostash and retry after confirming the working tree.

The GitHub plugin remote moved by two commits during this pass. There are no conflict files, so I’ll fast-forward with autostash, rerun its check, and retry the commit.

The GitHub plugin fast-forwarded cleanly. I’m rerunning its check on the new base before committing.

The GitHub plugin check passed on the updated base. I’m retrying its SASE commit now.

The GitHub plugin commit succeeded. I’m verifying it is clean, then I’ll commit the Telegram wording change.

`SASE-github` is clean. I’m committing the one-line Telegram ChangeSpec wording update now.

Telegram committed cleanly. I’m doing a final status pass across all four repos to make sure nothing is dirty or ahead of upstream.

All four working trees are clean and even with their upstreams. I’m collecting the final commit IDs for the summary.

Committed all finalizer-detected changes and verified clean status in every repo.

Commits:
- `sase`: `ba6d2a1e5 feat: use PR terminology for ChangeSpec reviews`
- `sase-core`: `bde760c feat: rename ChangeSpec wire review field`
- `sase-github`: `45cb817 feat: use PR terminology for GitHub review hooks`
- `sase-telegram`: `14f3c19 docs: clarify Telegram ChangeSpec wording`

Validation rerun after syncing updated upstream bases:
- `sase`: `just check`
- `sase-core`: `cargo fmt --all --check && cargo test --workspace`
- `sase-github`: `just check`
- `sase-telegram`: `just check`

Final `git status --short --branch` is clean and even with `origin/master` in all four repos.
