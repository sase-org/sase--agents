# Chat History - ace-run (sase-z4.5)

- **TIMESTAMP:** 2026-09-10 07:59:05 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-z4.5

## Prompt

#gh:gh_sase-org__sase
%id(5, clan=sase-z4, bead=sase-z4.5)
%model:@medium
%auto
%w(bead=sase-z4.4)
Can you complete the work for bead sase-z4.5? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-z4.5 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-z4.5`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-z4.5 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I’ll use the SASE bead workflow first, then the final declaration skill before I respond. I’m going to read the bead-specific instructions and inspect the assigned phase before touching code.

The `sase_beads` skill path from the skill list was missing on disk, so I’m checking the installed skill names before falling back to the CLI workflow. The final and memory-read skills are available.

I’ll proceed with the audited memory read for bead handling now. That should cover the project rules for inspecting and closing this phase despite the local skill file being absent.

I’ve loaded the bead lifecycle rules. Next I’m reading `sase-z4.5`, checking the repo state, and finding the linked design context so the code changes stay scoped to this phase.

`git status` is clean at the start. The bead commands are taking a moment, so I’m waiting for their output before deciding what to edit.

The phase is a rollout phase: apply workload weights to bundled epic landers and research swarm segments, update docs/package compatibility, verify integration, and remove rollout scaffolding. I’m reading the parent plan now to pin down the intended design details.

The plan confirms this phase is the final adoption pass after the core plumbing and UI phases. I need a narrower search next; the first repo-wide query was too broad because “weighted” appears in unrelated docs and tests.

This phase touches prompt directives, feature-flag rollout cleanup, and a linked research plugin. I’m loading the relevant project notes and the external-repo workflow before opening or editing anything outside this checkout.

I’m opening the linked research plugin through `sase repo open` now. The plan requires using that audited path before reading or changing the plugin.

The repository open is still running; I’m waiting for the audited path before touching plugin files.

The plugin path is available under the workspace’s linked-repo area. I’m reading its local instructions and checking whether either repo already has uncommitted changes.

Both worktrees are clean. I’m inspecting the current rollout state now: lander prompt, flag registry/consumers, docs, and the plugin swarm template/tests.

The plugin still has the old `runners=16` default. The main repo also still has the beta flag branch, so the rollout work is real rather than just documentation.

One important scope point: the plan mentions closing the temporary flag bead, but your launch instruction says to close only `sase-z4.5`. I’ll remove the rollout branch in code, and if the separate flag bead still needs lifecycle cleanup I’ll record that as a proposed follow-up on this phase rather than closing another bead.

The code has explicit flag consumers in the queue directive adapter and feature-flag tests. I’m also checking the dedicated flag bead’s state so I know whether to leave a lifecycle note later.

The flag linter treats a registered flag with no non-test consumer as an error, and a live flag bead without a registry entry eventually becomes an orphan error. I’m going to keep that constraint in mind while removing the actual user-facing gate.

The main code path only uses the `weighted_queue_capacity` flag in the queue directive adapter. Making weighted queues unconditional should be a small code change, but the docs/tests need to move from beta-gated behavior to the final contract.

The docs still describe runner slots as integer slots. I’m reading the exact sections that need to be changed to weighted capacity language and new preset behavior.

The lander prompt has no queue weight yet, and the research plugin docs/tests still assume integer-only queue control. I’m reading the launch tests that cover expanded `#bd/land_epic` so I can verify the actual rendered prompt, not just the config string.

The bead-work renderer deliberately emits `#bd/land_epic` rather than duplicating directive text, matching the plan. I’m looking at the built-in xprompt tests for a focused assertion that the resolved lander body carries `w=2.0`.

I’m going to verify the dependency floor with the repo’s existing probe instead of guessing package availability. The phase already has a note that some required core APIs may not be published yet, so I need current evidence before changing version constraints.

The core floor probe is still running. The current SASE lock already points at `sase-core-rs>=0.32.61,<0.33.0`; I’m waiting to see whether that published floor now contains every weighted-capacity API.

The floor probe could not complete because its binding-name collector hit a Python syntax mismatch while reading the core checkout. I’ll still inspect the opened core repo instructions before any further core-related checks.

The core repo open is still resolving. After that I’ll keep core access read-only unless a required compatibility change is clearly needed.

I have the core path. I’m reading its instructions and checking versions with the runtime we actually use for the SASE checkout.

The workspace venv has `sase-core-rs 0.32.61` installed. Since the advisory probe failed before checking symbols, I’m directly checking the required binding names in the installed distribution.

The installed floor exposes the weighted-capacity APIs, so the main SASE core dependency already satisfies this phase. I’ll check the plugin’s host-SASE floor separately, because its docs still say that release was not on PyPI.

PyPI is reachable. I’m going to query the JSON metadata in a small script so I can update or leave the plugin floor based on exact published versions.

The latest published `sase` is `0.17.1`; the plugin currently allows `0.17.0`. I’m checking release metadata so the plugin floor names the first published host version that actually brings the weighted queue runtime.

The metadata fetch is still downloading wheels. I’m waiting for the exact dependency lines rather than inferring from version numbers.

PyPI `sase 0.17.0` and `0.17.1` both allow `sase-core-rs>=0.32.16`, so neither published host package pins the current weighted-capacity binding floor. I’m checking whether the latest published host still has the beta rejection branch; that decides whether plugin publication needs a follow-up release.

The wheel layout didn’t have that file path, so I’m listing the relevant wheel members before drawing conclusions about published host behavior.

I’m going to edit the main repo to make queue weights unconditional, remove the registry/schema entry, and add `w=2.0` to the built-in lander body. Then I’ll update the affected tests from “beta gated” expectations to the final contract.

Before editing tests, I’m checking whether `override_flags` is used elsewhere in those files so I only remove what becomes stale.

I’m applying the main repo edits now: delete the beta gate code, remove the flag definition, update the lander prompt, and adjust tests that referenced the retired flag.

The main code/test patch is in. I’m regenerating the feature flag schema from the registry so the JSON stays canonical.

The schema sync completed cleanly. I’m checking for any stale references to the retired flag before moving on to the plugin changes.

I’m moving to the research plugin now. The template will use one `%q(w=0.25...)` directive per segment, keep explicit `runners=` as an optional count condition, and the tests will parse each expanded segment through SASE’s directive extractor.

The plugin’s dependency comment is stale now that `sase 0.17.0` and `0.17.1` exist on PyPI. I’m checking the host changelog before changing the plugin floor, because a published SASE package still needs to understand the weighted prompt it will load.

I’m editing the plugin template, dependency metadata, and tests now. I’ll add a direct `sase-core-rs>=0.32.61,<0.33.0` floor because the packaged prompt now requires the weighted `%queue` grammar even though the host SASE release floor still needs a follow-up release.

The plugin diff is mostly right, but I spotted a duplicate literal in one test and an import-order cleanup opportunity. I’m going to tidy those before running tests.

The duplicate was just an earlier combined-output artifact. I’ll still update the test comment/import order to match the new `%q` template.

I’m updating the plugin-facing docs and Justfile comments next so they describe the new quarter-weight preset and the current dependency floor accurately.

The plugin docs now match the template. I’m reading the main config defaults around `max_running_agents` so the SASE docs and schema use “capacity units” consistently.

The shipped config comment also still says “one slot.” I’ll update it to describe `max_running_agents` as a capacity budget while preserving the integer key and default.

I’m going to align the main docs with the implemented UI contract: capacity as `used/limit` units, running count as a separate status bucket, and `runners=` as an additional count condition rather than a cap override.

I’m patching the main documentation in targeted sections rather than trying to regenerate the full docs set. The changes are limited to queue syntax, capacity accounting, Launch Control, and troubleshooting text.

That patch missed one exact paragraph in `docs/ace.md`, so I’m splitting the documentation edits into smaller patches against the current text.

The directive completion table now includes `weight=`/`w=`. I’m updating examples and the queue semantics section next.

The old queue section is a clean contiguous block, so I’m replacing it with the final weighted-capacity contract.

The ACE section’s current text predates the capacity-prefix implementation. I’m replacing that block with the existing `C/L [running · queued]` behavior and weighted row-badge language.

The ACE docs are aligned. I’m updating configuration docs for `agent_runners`, `wait_runners`, and `max_running_agents`.

The generated table spacing is wider than my first patch context. I’m applying a narrower replacement.

Now I’m replacing the `max_running_agents` section itself so the integer config key is documented as a capacity budget, not a headcount cap.

I’m also updating the JSON schema description for `max_running_agents`; the validation type and minimum stay unchanged.

The config docs/schema are updated. I’m rewriting the runner-slot troubleshooting page around the new admission model and the lander/research presets.

The troubleshooting page now reflects weighted admission. I’m updating the smaller CLI JSON description too.

I’m scanning for remaining obsolete “slot/headcount cap override” language so I don’t leave contradictory docs behind.

The first stale-language scan found a few remaining sections in AXE, LLMS, and troubleshooting. One plugin scan had shell backtick expansion in the pattern, so I’ll rerun that safely after I patch the main docs.

I’m going to pick up from the existing edits, first checking the remaining stale references and the changed file set so I can finish the rollout without reopening unrelated work.

The remaining stale text is in docs, not code. I’m going to patch those references to talk about capacity units and count guards consistently, then add a focused built-in lander test for the new `%q(w=2.0)` preset.

I’m editing only the stale doc language and one narrow test. The goal is to keep existing implementation names where they still exist, but describe their behavior as weighted capacity instead of slot/headcount where user-facing semantics changed.

The stale wording scan is clean for the targeted phrases. Next I’m checking for leftover `weighted_queue_capacity` references and then I’ll run the repo’s required verification path.

There is one leftover enforcement hook in the Rust launch facade that still imports the removed rejection helper. I’m removing that Off-branch check so typed launch planning treats queue weights as always supported.

The feature flag symbol scan is now the important one: any remaining `weighted_queue_capacity` or disabled-weight helper references would mean the rollout is not complete.

Because this changed tracked files in the main SASE repo, I’m reading the repo’s required verification memory before running the final test suite.

I’m going to run formatters before tests so any import/order or Markdown wrapping issues show up as actual verification failures only if the formatter cannot settle them.

The plugin formatter triggered its local install path and is building the linked Rust core into the plugin virtualenv. I’ll wait for that to finish before starting checks so the environment is consistent.

The Rust extension build is still active; no failure yet. Once it returns, I’ll run the focused tests and then the full `just check` gates.

The build is still running quietly. I’m keeping the session open and polling it rather than starting overlapping verification that would compete with the same environment.

Still no new output from the Rust build, which is normal for a release compile here. I’ll keep waiting on the formatter/install command to complete before moving on.

The linked core build is still holding the verification lane. I’m waiting it out because interrupting it would leave the plugin env half-prepared.

The build reached the Python extension crate, so it’s near the end of the plugin environment setup. After that I’ll run the plugin checks and wheel test.

No new output yet, but the process is still alive. I’ll give the release build another poll window; if it finishes cleanly, the remaining checks should be straightforward.

The build has been quiet for a while, so I’m checking the process tree to confirm it is actively compiling and not waiting for input.

That process-tree check did not target the tool session cleanly, but the session itself is still responsive. I’ll continue polling the actual command output.

The plugin command is actively inside `rustc` for `sase_core_rs`, so it is not blocked. I’ll let that compile finish and then continue with the test gates.

Formatting completed. I’m running the focused tests that cover the changed surfaces now, with the plugin’s full `just check` in parallel.

The focused SASE tests passed. The plugin `just check` is through lint/mypy and most tests; I’m waiting for the rest of that suite to finish.

Plugin `just check` passed. I’m running the required main `just check` now, plus the plugin wheel contract test the phase explicitly called out.

Both required gates are in flight. The main repo has cleared the early format and ruff checks; the plugin wheel test is on its fresh-venv install smoke.

Main `just check` has passed mypy and is moving into the heavier gates; the plugin wheel smoke is still running without errors.

Both processes are still active and quiet. I’ll keep polling rather than start any additional work that could interfere with the verification load.

The main check has cleared feature-flag and script lint, which is the critical area for removing the rollout flag. The plugin wheel test is still in the install smoke.

Main lint continues to pass through the repo-specific gates. I’m still waiting on both sessions to complete before I touch bead closure.

Main `just check` has passed symvision and toobig. It should now be in the scoped pytest lane; I’ll wait for the final result.

The main check emitted the expected core-floor probe warning: those Rust symbols are present locally but not contained in a released `sase-core` tag yet. That matches the existing follow-up note on the bead; I’m waiting for the command’s final exit status before deciding whether anything else is needed.

The plugin `just test-wheel` passed. Main `just check` continued past the core-floor probe and is still running; I’m waiting on the final scoped tests.

Main `just check` is still active with no new output. I’ll keep it open; the plugin verification is complete.

Still no new output from the main check. I’m continuing to wait for the command’s exit status rather than assuming the gate passed from partial output.

The main check is taking longer than the targeted pytest suite, likely in the scoped selection/test lane. I’ll keep polling until it finishes or reports a concrete failure.

The check has been quiet long enough that I’m checking the process list again to see which subcommand is currently running.

Process inspection shows the main check is in `just test-scoped` for this workspace, with other background SASE checks also running on the host. I’m waiting for this workspace’s session output rather than relying on the global process list.

No new output yet from the scoped pytest lane. It is still active, so I’m continuing to wait for the actual exit status.

The scoped lane remains quiet. Since it is part of the required repo check, I’m letting it continue rather than replacing it with a smaller command.

Still waiting on `just check`. The elapsed time is high but the process is still present; I’ll keep this lane open until it returns.

I’m checking the specific pytest process for this workspace to see whether it is still consuming CPU or simply waiting.

The scoped pytest workers are active and using CPU, so this is a long test run rather than a hang. I’ll keep waiting.

The main scoped test lane is still running. I’m letting the repo’s selected test set finish because this phase touches shared launch/xprompt behavior.

No change yet from the main check output. The worker processes were active on the last inspection, so I’m continuing to wait for completion.

The main check remains in the heavy scoped pytest phase. I’m waiting on the final result and keeping the session open.

Still waiting. The command is not producing intermediate pytest progress because it’s wrapped by `tools/run_silent`, so the next output may be only the final pass/fail summary.

The scoped test run is still active. I’m going to let it continue; interrupting now would leave us with less useful verification than the required `just check`.

Still no final output. I’m continuing to wait because the workers were active and this is the required gate for tracked main-repo changes.

I’m doing one more process check to confirm the main scoped tests are still making progress and to rule out a dead worker.

The pytest workers are still active and using CPU across the selected tests, so the run is progressing. I’ll continue to wait for the final summary.

Main `just check` passed; its scoped lane escalated to the full suite and still completed successfully. I’m checking the final dirty state and then I’ll handle bead bookkeeping.

The dirty set matches the rollout scope across the main repo and the research plugin. I’m doing a quick self-review pass now, including whitespace checks and the critical code/config diffs, before touching bead state.

Self-review found two small quality issues: a generic `pytest.raises(Exception)` and plugin dependency prose that implied the current core floor is a fully published weighted-capacity release. I’m tightening those before rerunning the affected checks.

I’m making those last self-review edits now: restoring the specific directive exception assertion and changing the plugin floor comments/docs to say this is a coordinated-source floor until the weighted-capacity core release is published.

I changed one Python assertion and a couple plugin docs/comments, so I’m rerunning formatting for both worktrees before the final verification repeat.

The main formatter is done. The plugin formatter is rebuilding the Rust extension again after the pyproject edit; I’ll wait for it to finish before rerunning the affected plugin gates.

The rebuild is progressing through the linked gateway/core crates. I’m holding until the formatter/install command exits cleanly.

Still building; no failure output. I’ll continue polling this session.

The release build is quiet again but still running. I’m waiting it out.

Still no new output; I’ll continue to wait for the plugin formatter build to complete.

The build reached `sase_core_py`; this should be the last Rust crate before the formatter returns.

The final extension crate is still compiling. I’ll keep waiting and avoid launching new checks until this environment step finishes.

Still waiting on the plugin formatter’s release compile. The process has behaved the same way as the earlier successful build, so I’m continuing to let it complete.

The build is still running quietly. I’ll poll it a bit longer; the previous full rebuild took several minutes in this same step.

Formatting is complete again. I’m rerunning the required main `just check` after the final test edit, and rerunning the plugin `just check`; the plugin wheel contract already passed after the template/package changes and the later plugin edits were prose/comment-only.

The repeated plugin check is through lint/mypy and most of its tests; main check is again through the early lint gates. I’m waiting on both final statuses.

Plugin tests are near the end; main has cleared mypy. I’ll keep polling until both commands exit.

The repeated plugin `just check` passed. Main `just check` is still running; I’ll wait for its final result.

Main has again cleared feature-flag and script lint after the final edits. I’m waiting through the remaining gates.

The repeated main `just check` failed in the patch/stitch terminology audit, but the findings are all in the linked `sase-core` migration file, not in the files I changed for this phase. I’m checking the linked core state to decide whether this is a pre-existing blocker or something I should resolve in scope.

The linked core worktree is clean, so this is an existing audit gap surfaced by the main check. I’m looking at the audit’s local allow/classification mechanism; if it’s a small source annotation, I can fix the check without changing behavior.

The repeated main check still stops at the same linked-core terminology audit findings before it can reach tests. I’m inspecting the audit classifier now; this looks like legacy migration compatibility that probably needs an explicit retained-token classification in `sase-core`.

The audit classifies retained legacy tokens from nearby context. The linked-core migration code is compatibility logic, so I’m going to add a concise compatibility comment near those checks in `sase-core` and rerun the main check.

I’m adding a named legacy-heading constant in the linked core migration module. That keeps the compatibility token in one explicitly classified place and removes the unclassified repeated literals.

That linked-core edit is source-only and should be rustfmt’d. I’m formatting that repo and then rerunning the terminology audit before the main check.

The targeted `ChangeSpec` scan now shows only the classified constant and test fixtures. The terminology audit itself is still running; I’m waiting for its result.

The terminology audit now passes after the linked-core compatibility annotation. Since that touched `sase-core`, I’m running both the main repo `just check` again and the linked core `just check` before closing the bead.

Core `just check` is queued on Cargo’s build-directory lock, likely behind another core test already running on this host. Main check has started. I’ll wait on both.

Main has cleared fmt, ruff, and mypy. Core is still waiting on the Cargo lock, so I’m keeping both sessions open.

No new output from either check. The main check is still running; core remains blocked on the build lock.

Both checks are still active and quiet. I’ll continue to wait; there is no actionable failure yet.

Main has cleared the feature-flag lint after the flag removal. Core is still waiting on the Cargo lock; I’m continuing to hold both sessions.

Main now passes the terminology audit too; it’s into the remaining validation/test phases. Core is still lock-waiting.

Main has cleared symvision and size checks. I’m waiting for the validation/core-floor/scoped-test tail and for core’s Cargo lock to free.

Both sessions are still running quietly. I’ll keep waiting for the final check output.

Main reached the expected unpublished core-floor warning again, then continued past committed-plan checks. I’m waiting for the scoped/full test lane and for core’s Cargo lock.

No final output yet. Both sessions remain open; I’ll continue polling.

Still waiting. The main check is likely in the silent pytest wrapper again, and core is still blocked on Cargo’s shared lock.

Both checks are still active and quiet. I’ll hold until they return.

No output yet from the main test lane or the core lock wait. I’m continuing to wait.

This is another long quiet stretch, so I’m checking process state to make sure both verifications are still legitimately running.

Both verifications are active: main is in the scoped pytest runner and core has moved from lock wait into Cargo build/test work. I’ll keep waiting.

No final output yet. I’m continuing to wait on both check sessions.

Core is now in `cargo check` for `sase_core`; main is still in the test lane. I’ll continue polling.

Both checks remain active. I’m waiting for the final summaries.

Core check is through gateway, LSP, and Python binding crates. I’m still waiting on final results from both repos.

Core completed one dev build phase and is waiting on Cargo locks again for the next phase. Main’s test lane is still silent and active.

Core is now running its Rust test suite; output is large and truncated by the tool, but no failure has appeared. Main is still in its silent pytest lane.

Linked-core `just check` passed the Rust unit and integration tests it could run, then failed only when the `sase_core_py` test binary could not find `libpython3.14.so.1.0`. I’m checking the core repo instructions for the expected environment fix before deciding how to rerun.

The core check script selected Python 3.14, but its test binary needs that interpreter’s lib directory on `LD_LIBRARY_PATH`. I’m going to rerun core `just check` with that environment set; this is the same gate, with the missing runtime library path supplied.

The core rerun with `LD_LIBRARY_PATH` is now past the first build/check phase. I’m also waiting on the main repo check that is still running.

Core is waiting for the next Cargo lock again; main is still in its silent test lane. I’ll keep polling both.

The core rerun still exited 127, but the visible output was truncated before the failing tail. I’m going to capture the core test phase to `/tmp` and show the last lines so I can see the actual missing runtime piece; main check is still running separately.

That diagnostic command tripped zsh’s readonly `$status` name before running the test. I’m rerunning it with a neutral variable name.

The targeted core test phase passes with the library path set. The full core `just check` rerun with that same environment is still open, as is the main repo check, so I’m polling both for their final exit statuses.

The linked-core `just check` passed with `LD_LIBRARY_PATH` set for Python 3.14. Main `just check` is the only remaining open verification session.

Main is still running silently in its pytest lane. I’ll keep waiting for the final `just check` result.

No new main-check output yet. The earlier run took several minutes in this lane, so I’m continuing to wait.

Still waiting on the main repo check. No failure output has appeared.

The main check is still quiet. I’ll keep the session open until it exits.

All required verification now has passing results. Before closing `sase-z4.5`, I’m checking the related flag bead state because the rollout removed the `weighted_queue_capacity` registry entry, but this phase’s instructions only authorize closing `sase-z4.5`.

The three worktrees now show only scoped modifications: main rollout, research plugin rollout, and the single linked-core terminology annotation needed for the main gate. The flag-bead detail command is still returning.

`sase-z5` is still open and says its removal condition is this rollout. Since the phase instructions explicitly authorize closing only `sase-z4.5`, I’m recording that as a proposed follow-up on this phase rather than closing the flag bead myself.

The follow-up note is recorded. I’m now running the required epic-symbol check for `sase-z4.5`; if it reports leftovers, I’ll resolve them before closing the phase.

`epic-symbols` reports no leftovers for `sase-z4.5`. I’m closing only that phase bead now with the verification summary.

The phase bead is closed. I’m doing a final read-only status check across the touched worktrees, then I’ll run the SASE finalizer declaration as the last tool action before responding.

The bead is confirmed closed and contains the verification note plus the two follow-up notes. I’m now running the SASE finalizer context; after any required finalizer submission I won’t mutate the worktrees further.

The finalizer requires a commit declaration for three dirty repositories. I’m going to submit the manifest with separate messages for main, linked core, and the research plugin.

I’ve confirmed the finalizer rules. Submitting the commit declaration now; this is the last tool action before my final response.

Completed and closed `sase-z4.5`.

Implemented the weighted rollout across the main repo and research plugin:
- `bd/land_epic` now starts with `%q(w=2.0)`.
- Queue weights are unconditional; removed the `weighted_queue_capacity` flag/off-branch plumbing.
- `research_swarm` now gives all four segments `%q(w=0.25)`, with `runners` defaulting to null and only rendering when supplied.
- Updated docs/schema/tests/package compatibility text.
- Added a small linked-core audit annotation so the main `just check` terminology gate stays green.

Verified:
- Focused main pytest: `135 passed`.
- Main `just check`: passed; scoped lane escalated to full suite.
- Research plugin `just check`: `45 passed, 4 deselected`.
- Research plugin `just test-wheel`: `4 passed, 45 deselected`.
- Linked core terminology audit: passed.
- Linked core `just check`: passed with Python 3.14 `LD_LIBRARY_PATH`.
- `sase bead epic-symbols sase-z4.5`: no entries.

I also recorded a `PROPOSED FOLLOW-UP` note for existing flag bead `sase-z5`; I did not close it because your phase instructions authorized closing only `sase-z4.5`. Finalizer declaration was accepted for the three repo commits.
