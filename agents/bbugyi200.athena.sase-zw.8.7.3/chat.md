# Chat History - ace-run (sase-zw.8.7.3)

- **TIMESTAMP:** 2026-09-15 11:20:55 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-zw.8.7.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-zw.8.7, bead=sase-zw.8.7.3)
%model:@medium
%auto
%w:sase-zw.8.7.2
%w(bead=sase-zw.8.7.2)
Can you complete the work for bead sase-zw.8.7.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-zw.8.7.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-zw.8.7.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-zw.8.7.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I’ll use the SASE bead workflow first so the status/close mechanics stay in bounds, then I’ll read the phase design and make the code changes in the local workspace.

The bead skill path listed in the instructions isn’t present at that exact location, so I’m checking the local skill tree and will fall back to the SASE CLI workflow if the wrapper is missing.

The dedicated `sase_beads` skill is absent from disk, but the project also requires the audited memory read for bead rules. I’m loading that now before touching the bead.

I’ve got the finalizer rules too, so I’ll save that for the very end. Next I’m reading the bead rules through the audited memory command, then I’ll inspect `sase-zw.8.7.3` itself.

The bead rules match your constraints: no manual status writes, phase workers record follow-ups as notes, and close only the phase. I’m inspecting the bead and its referenced plan/design now.

The phase depends on the prior cleanup-safety phase and currently has no `--epic-symbol` entries, so there’s nothing stale to re-key before work begins. I’m opening the plan file named by the bead next and will trace the exact code paths from there.

The phase is the `runs` slice of the disk-retention safety epic. It points to the landing audit artifacts for the exact reproductions, so I’m loading the artifact rules and repo-opening rules before reading those or touching `sase-core`.

The plan’s `runs` section is very concrete: three Rust owner safety gaps plus a small Python user-surface piece. I’m reading the cited audit snapshots next so I can target the reproduced failures instead of wandering into the later phases.

The audit reproductions confirm this phase really is about deletion safety: symlinked run ancestors, protected empty runs, stale/incomplete protection coverage, and an hourly preview that needs a user-action surface. I’m reading the main and core code around the run owner and caller now.

I’ve opened `sase-core` through the audited repo command and found the run-retention modules in both repos. Before edits, I’m checking the local instructions in that linked repo plus the exact APIs and tests already in place.

There’s already a Python “recollect protections before apply” wrapper, but the core owner still only sees caller-authored strings and the empty-shard pass lacks the same protection set. I’m drilling into the lower half of the Rust owner and the Python protection model before patching.

The Python wrapper already blocks apply when the fresh scan/continuation protections are unavailable. The remaining stale-reference hole appears to need a stronger core contract: carry authoritative protected paths/timestamps into Rust and have the mutation pass enforce them, including for empty-shard cleanup.

The protection collector already records both exact directories and timestamps from sidecars/index/state. I’m checking the bridge and binding registration now, because adding authoritative protection fields means keeping the Python and PyO3 schemas aligned.

I hit one typo in a search path, but the useful reads landed. The preview chop currently only logs counts and marks protection issues as `check_error`; I’m looking for the existing gate/notification primitives it should reuse.

The hourly config names `artifact_run_prune` as a preview-only chop, so the surface change can stay local to that chop plus the existing notification store. I’m checking the chop SDK and notification model to keep deduplication consistent with the rest of Axe.

The notification store has an `upsert_notification` path keyed by `(sender, dedup_key)`, which is exactly the right shape for unchanged previews: create once, then add a lightweight occurrence instead of spamming the inbox.

The docs already promise that actual deletion still requires explicit `sase artifact prune-runs --apply` or a follow-up gate. I’m going to make the hourly preview raise a deduplicated report-style notification pointing at that existing command surface, while the core fixes make any apply fail closed.

For the actionable preview I can attach a validated chop report to a `ViewReport` notification and include the CLI command in the report body. That gives the user something clickable without making the hourly job perform deletion.

While tracing the empty-shard walk, I found another plan item already visible in code: preview ignores the apply removal budget. I’m going to fix that in the same Rust pass so the dry-run count cannot promise more shard removals than apply would attempt.

I’ve got the core patch shape now: schema v2, authoritative protected dirs/timestamps, lexical symlink checks before canonicalization, valid run-path checks, and a shard walker that only touches month/day/run structure and consumes the same budget in preview and apply.

Before editing I’m checking the PyO3 marshalling entrypoint, just to confirm serde handles new defaulted request fields without extra hand-written conversion.

The Rust side uses serde for the request object, so the new v2 fields only need model definitions plus the Python request payload. I’m patching core first, then I’ll wire the Python preview/report layer.

I’m making the Rust edits now. The important bit is that the owner will validate the path as written before resolving it, then compare the resolved path to the exact canonical `project/artifacts/ace-run/YYYYMM/DD/timestamp` location.

The first patch is in; I’m doing a quick compiler-oriented read of the edited Rust to catch type issues before I stack tests on top.

I caught one Rust slice comparison and the test request builder needs the new v2 fields. I’m adding focused Rust regressions for the audit’s symlink and protected-empty-run cases while I’m in this file.

One more small internal adjustment: empty-shard cleanup should also preserve runs that apply skipped after the fresh marker recheck, not only runs protected during preview classification. I’m folding that in before the tests.

Now I’m adding the focused Rust tests: one for the symlinked ancestor reproduction, one for authoritative timestamp protection, one for protected empty runs surviving the empty pass, and one for preview budget parity.

The Rust regression coverage is in place. I’m wiring Python to send the authoritative protection snapshot into schema v2 and then I’ll add the hourly notification/report behavior.

Python now speaks the v2 wire contract. I’m checking for schema-version fixtures and then I’ll patch the notification path.

The broad schema search was noisy, but the only run-retention-specific fixture outside the edited module is a PyO3 export-list expectation. I’m opening that narrow section before continuing.

The v2 schema scan didn’t show any hand-maintained run-retention fixture that needs changing beyond the code I touched. I’m formatting the Rust now so the next compiler run gives real signal.

The notification path can solve deduplication, but a command-backed gate would be a heavier integration. I’m checking the existing gate creation surface briefly; if it is straightforward, I’ll use it, otherwise I’ll use a report notification that names the exact apply command and remains preview-only.

A custom command gate is doable, but it brings request bundles, pending-action registration, and user answer execution into a housekeeping chop. I’m going with the lower-risk supported path: a priority `axe` notification with a validated report and stable dedup key.

I’m editing the chop script now. It will still return the same compact summary, and when there is either reclaimable run/shard work or a protection-source problem it will upsert one `axe` report notification keyed by a fingerprint of the current preview.

The chop now builds a `ViewReport` notification with the apply command but does not run it. I’m adding output-contract tests around the notification path, including the protection-unavailable case.

For the Python side I’m adding “real binding” tests by calling the PyO3 run-retention entrypoint with temporary directories. These mirror the audit repros without relying on the higher-level collector to paper over core behavior.

I noticed the symlink test can be clearer with a normal `os` import, and I’m tidying that before running formatters.

The focused Python binding tests are in. I’m updating the shipped hourly-chop descriptions next so the documented behavior matches the new notification/report surface.

There is a generated-style configuration doc copy of the same chop text, so I’m keeping that in sync as well.

I found the duplicate configuration prose. I’m patching only those lines so the generated docs stay coherent with the default config.

The code and docs are patched. I’m running focused Rust tests now, then I’ll run the Python focused tests against the rebuilt binding path.

The Rust focused test is still compiling the workspace dependencies; no failure yet. I’m letting it finish before touching anything else.

Still compiling; this checkout had a cold-ish Rust build, so the silence here is normal. I’ll wait for the actual test output.

Focused Rust run-retention tests pass: 13/13, including the new safety cases. I need the Python tests to load the edited PyO3 binding, so I’m checking the local install target before running them.

The focused Rust tests are green, and the changed tree is exactly the run-retention slice plus docs/tests. I’m rebuilding the editable Rust binding into this workspace venv so the Python binding tests exercise schema v2.

This workspace doesn’t have a `.venv/bin/python`, so that install target rejected the explicit venv path. I’m checking the active Python/uv-tool layout and will use the repo’s uv-tool install target if that’s what this checkout is using.

That was just a Justfile calling convention mistake on my side: the recipe takes the venv as a positional argument, not `VENV=...`. The venv itself is healthy, so I’m rerunning the install correctly.

The editable PyO3 build is underway. Once it installs, I’ll run the Python focused tests that exercise the new binding contract.

Still compiling the local wheel; this is the expected longer path because the core checkout is dirty and cache lookup correctly missed.

The build has reached the edited `sase_core` crate now. If anything is off in the v2 structs, this is where it should surface.

No error yet; the wheel build is still running in the final link/package stage.

Still alive and building. This is the expensive part, but it’s better than running the Python tests against the stale wheel and getting false negatives.

The local binding build is taking a few minutes, still with no failure output. I’ll keep the session open until it finishes.

Still compiling/linking; nothing to act on yet.

The build remains in progress; I’m waiting rather than interrupting since it’s the install gate for the Python side.

The install target has moved past core into the gateway crate, so the workspace build is still making progress.

Still in the Rust workspace build. No failures so far.

Now it’s compiling `sase_core_py`, the actual extension module. We’re close to the Python test pass.

Still linking the PyO3 extension. I’m holding the turn open until it returns.

No output yet from the linker/package step; still waiting.

The install is still running and has not emitted an error. I’ll keep polling; there’s no safe partial shortcut here.

Still building. The Rust extension can take a while on a fresh target, but the process is alive and quiet.

No change yet; I’m continuing to wait for the install command to terminate cleanly or fail with useful output.

Still in progress. I’m avoiding parallel changes while the local wheel build is using the same tree.

The extension installed successfully as `sase-core-rs 0.34.32`; the recipe is now building the paired LSP binary. I’ll let the install recipe finish fully, then run the Python checks.

The LSP build is also progressing. Nothing failed in the extension install, which is the key dependency for the tests I added.

Still building the paired LSP. This should be the last large compile step.

No error output; still waiting on the LSP build to finish.

It’s compiling the final `sase_xprompt_lsp` crate now.

The editable binding install completed cleanly. I’m formatting the touched Python files, then running the focused Python regression tests.

Formatting is clean; one test file was reformatted. I’m running the focused Python tests now against the freshly installed binding.

The focused Python run found a test typo, not a product failure: I used Rust-style `parent()` on Python `Path`. I’m fixing that and rerunning the focused tests.

The typo is patched. Running the same focused Python tests again now.

Focused Python tests are green: 15 passed. Since this turn changed tracked files in the main repo, I’m loading the project’s lint/test memory before selecting the broader verification lane.

The verification memory requires `just check` for main, and the linked core repo asks for its own `just check` before commit. I’m starting with the core check because that’s where the shared retention owner changed.

Core `just check` is compiling/checking the full workspace now. I’ll wait for the clippy/test output before making any more changes.

The core check is still moving through the workspace. No compiler or clippy diagnostics yet.

Core `just check` finished the first cargo check stage and has moved into the test/clippy phases. Still healthy.

Still progressing through the full core check. No diagnostics to fix yet.

The full core check is in the longer cargo test build stage now. I’ll keep polling until it completes.

Core check continues; it has reached the workspace binaries again.

Core `just check` got through the Rust test suite but failed at the PyO3 test binary loader because `libpython3.14.so.1.0` was not on `LD_LIBRARY_PATH`, which matches the known project caveat in the acceptance evidence. I’m rerunning core `just check` with the interpreter library path set.

The rerun with `LD_LIBRARY_PATH` is past the PyO3 loader point and through the workspace tests; it’s in doc-tests now.

Core `just check` passes with the documented Python library path. I’m moving to the main repo `just check` now, which is the required SASE verification lane for changed tracked files.

Main `just check` refreshed the editable install and required plugins, then passed Python formatting, Markdown formatting, keep-sorted, and Ruff so far. It’s continuing through the rest of lint/tests.

Mypy passed. Waiting on the remaining main checks.

Still running; the quiet stretch is likely Symvision or test selection. I’m waiting for the next concrete result.

Feature-flag and script lint passed. Main check is still going.

More lint gates passed, including changelog and terminology. Waiting on the last lint gates and scoped tests.

Symvision and file-size lint passed. The run is into the scoped pytest selection now.

Scoped tests are still running. No failures reported yet.

Repository validation and committed plan checks passed. Still waiting on the test lane output.

The scoped pytest lane is taking the bulk of this main check. I’ll keep it running to completion.

Still no failure output; scoped tests continue.

The main check is still active and quiet. I’m not interrupting it; this is the required gate for the main repo changes.

Still running. The lack of output just means pytest hasn’t printed its summary yet.

Another quiet interval, still active. I’ll keep polling until it returns.

Main check continues. No failures have appeared.

Still waiting on pytest. This one is longer than the focused suite but still within normal `just check` territory.

No new output yet; the required main check remains active.

Still no summary from `just check`. I’m continuing to wait rather than cutting off the verification run.

The check is still alive and quiet. I’ll keep it going to the final status.

Another quiet 30 seconds. Still waiting on the main test lane.

Still running. No failures or prompts have surfaced.

The main check is still active; I’m holding for completion.

Still no terminal result from `just check`. I’ll keep polling; everything before pytest was green.

Main verification remains in progress. No action needed yet.

Still active and quiet. I’m giving it more time.

`just check` is still running without output; that can happen with a large scoped xdist selection. I’m going to give it another poll rather than launch competing diagnostics.

Still no summary. Holding the verification run open.

This has been quiet long enough that I’m going to inspect the running process tree without interrupting it, just to see whether it’s in pytest, Cargo, or waiting on something else.

That process-tree check only saw its own shell because the verification session has a separate process group. I’ll poll the original session again for the authoritative result.

Main `just check` escalated to the full suite and finished 41,762 tests, with one failure: `tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess`. I’m rerunning that single failure to see whether it is real, flaky, or tied to the editable install refresh.

The single failing test passed immediately on rerun, so I’m treating that as a discovered full-suite flake rather than a retention regression. Per your instruction, I’m recording it as a `PROPOSED FOLLOW-UP` on this phase instead of creating a task bead.

The bead note command is still running, likely publishing the sidecar update. I’m waiting for it to settle before rerunning the main check.

The proposed follow-up note is recorded. I’m rerunning main `just check` once more so the close note can name a clean required gate rather than a failed run plus a focused rerun.

The second main `just check` has already passed formatting, Ruff, and mypy. It’s continuing through the remaining lint gates and tests.

Feature-flag lint passed on the rerun. Still going.

Script lint, test-wait lint, changelog, and terminology passed on the rerun.

Symvision and toobig passed again. The rerun is entering validation/tests.

Still running. No failures have appeared on the rerun so far.

Validation and committed plan checks passed on the rerun. Waiting on the full-scoped pytest lane again.

The rerun’s pytest lane is active and quiet. I’ll keep it going.

No test failures reported yet; still waiting on the rerun.

Still running. The second pass is behaving like the first: long full-suite selection with sparse output.

Still active, no new output.

The main rerun is still in pytest. Holding.

No output yet from pytest; still waiting for the final summary.

Still active. I’m keeping the turn open for the required verification result.

Another quiet interval. The rerun hasn’t surfaced a failure.

Still waiting on pytest.

The main check rerun remains active; no new output yet.

Still active and quiet. I’m waiting for the suite summary.

No final summary yet. Holding.

Still running. The previous full-suite lane took about eleven minutes; this rerun is in the same range.

Still no output from the pytest workers. I’m continuing to wait.

The suite is still active. No failures printed.

Still waiting. This is long, but the process is still alive.

No change yet. I’ll keep polling until it returns.

Still active and quiet.

Still running. The full suite is not giving progress output between chunks, but the session is alive.

I’m picking up where the run left off: the implementation and focused checks are done, and I’m waiting on the second full `just check` result before I touch the bead state. After that I’ll re-check epic symbols, close only `sase-zw.8.7.3`, and run the SASE final declaration.

The previous terminal session handle didn’t survive the context handoff, so I’m checking whether that process is still alive. If it isn’t, I’ll rerun the required check cleanly rather than guessing.

The full check is still running as a detached `just check` process, so I’m going to let it finish rather than start a second full-suite run on top of it. Since the original output stream is gone, I’ll use the result cautiously: if I can’t recover an exit status, I’ll rerun what’s needed after it exits.

It’s only a few minutes into the full suite, which usually takes a while here. I’ll keep an eye on it and avoid piling more load onto the machine.

The detached check is still in its Rust/PyO3 build setup step, so the long part hasn’t really begun yet. I’m going to poll at intervals; no code changes from here unless verification turns up something real.

Still waiting; this is just a short poll delay so I don’t spam the process table while the suite warms up.

That polling delay finished. I’m checking the process tree again now to see whether the suite has moved into Python tests or finished.

It’s still rebuilding the extension module, which explains the quiet spell. I’ll wait another bit; once this exits, I’ll decide whether the lost output forces a final rerun of the check.

No new result yet; still letting the machine breathe through the full check.

Another quiet interval; I’m keeping the wait external and boring so the actual test run can finish cleanly.

Still waiting. The important bit is that I haven’t made any more changes; we’re strictly in verification/closure territory now.

The wait finished; I’m checking whether the detached `just check` finished too or moved into the next stage.

Still in the extension build at six minutes. That’s slower than the prior focused install, but plausible for the full check path after touching the Rust core; I’m going to give it a longer interval now.

I’ll be quiet for a short stretch while this build/test process gets through its slow part.

Still waiting; no changes, just verification patience.

One more poll interval; after this I’ll re-check the actual process tree so we know where it is.

The timer is still running; I’m letting it complete this interval and then I’ll inspect.

Almost through this wait. I’ll do one final poll and then check the process state.

The longer wait is done. I’m checking whether the full suite is now in pytest or has already finished.

The check moved past the Python extension build and into the xprompt LSP build step. That’s progress, but because the original terminal handle is gone I’m still treating this as a live load-management check, not as captured verification.

The detached process is writing to pipes owned by the runner, so I can’t safely recover the live output from here. I’m going to let it finish and then do one captured verification pass if needed.

I’m settling into a longer wait now. Once the detached check exits, I’ll start a fresh captured `just check` only if there’s no auditable result to cite.

Still waiting on the detached verification process; no intervention needed yet.

Another poll interval passing. I’m keeping the check isolated so I don’t turn verification into a resource fight.

Still in the wait window. Once this timer ends I’ll inspect the actual test process again.

No visible result yet; this is the slow but necessary part.

Still waiting; I’ll check the process tree after this longer timer completes.

The timer is still alive; holding steady.

One more quiet interval before I inspect the detached check again.

Almost done with this wait window.

The timer has slightly outlived its nominal duration, so I’m polling once more to let it exit cleanly.

The wait is complete. I’m inspecting the detached `just check` now.

Now it’s in the full scoped pytest lane with 14 workers, so the costly build phase is over. I’ll continue waiting; after it exits, I’ll run whatever captured check is still necessary.

The full test lane is running; still just verification.

Still waiting on pytest workers.

No result yet; I’ll keep polling at steady intervals.

Still in the full pytest run. Nothing to act on yet.

The suite is still running; I’m waiting this one out.

Another interval, still no visible exit.

Still running; I’ll inspect the process tree when this wait window completes.

The timer is nearly done.

One more poll for the wait timer, then I’ll check whether pytest is still alive.

The wait completed. I’m checking the detached check’s state again.

Pytest is still actively working. I’m going to quickly inspect the project’s silent-run wrapper to see whether it leaves a log file I can read after the detached check finishes.

The wrapper only preserves detailed output on failure unless monitor artifact env vars are set. I’m checking the detached process environment to see whether it will leave auditable stage diagnostics.

Good, the process does have SASE diagnostics directories, so the runner may leave stage records. I’ll use the artifact CLI for any artifact reads so they’re audited.

I’m checking the artifact index for any monitor-stage entries tied to this check. Listing via `sase artifact` is safe; if I need content, I’ll use `sase artifact read`.

No indexed stage entries yet, likely because the wrapper records them only after each stage finishes. I’m going back to waiting on the active pytest run.

Still waiting on the full pytest lane.

No visible change yet; I’ll keep polling.

Still running. The first full run took about eleven minutes once tests started; this one is a little slower, but not outlandish.

Another interval; still verification only.

No exit yet. I’ll inspect after this wait completes.

Still waiting; the process is getting a little long, so I’ll check it soon for signs of a hang.

One more interval before a process-tree check.

The wait timer is nearly done.

Finishing this wait window now, then I’ll inspect the live workers.

The wait is done; checking the detached run again.

The detached `just check` process has exited. I’m looking for the SASE stage diagnostics it should have recorded; if they don’t give a clear pass/fail, I’ll rerun a captured check.

No indexed artifact surfaced for that stage. I’m checking the recent artifact list once before deciding whether to rerun.

I don’t have a reliable exit status from the detached run, so I’m starting a fresh captured `just check` now with the Python 3.14 library path set. The earlier build work should make this mostly the test lane rather than another cold rebuild.

The captured check is underway and already through formatting, ruff, and mypy. I’ll keep polling until it finishes.

Still moving through the lint/validation gates; so far clean.

The lighter gates are passing; waiting on the remaining validation and test stages.

Symvision and size checks passed. Next up should be SASE validation and the scoped test run.

No new line this interval; still in the check pipeline.

Validation and committed-plan checks passed. The suite has entered the scoped/full test lane now.

Tests are running; waiting for results.

No result yet; still in pytest.

Still running. Full scoped tests are intentionally quiet unless something fails.

Another interval, still waiting on test completion.

Tests are still active. No evidence of a code failure yet; just quiet workers.

Still waiting.

No output this round; I’m continuing to poll.

Still in the test lane. I’ll stay with it until we get a terminal result.

Another quiet interval; full-suite patience tax, alas.

Still running cleanly from the outside; waiting for the final line.

No final status yet. I’ll keep polling.

Still waiting on pytest.

The test run is still quiet; continuing.

Still running. We’re roughly in the same time band as the earlier full run now.

No result yet; staying with it.

Still waiting.

Great, the captured `just check` passed, including the escalated full-suite lane. I’m doing the required epic-symbol sweep now, then I’ll close only the phase bead.

No epic-symbol leftovers. I’m closing `sase-zw.8.7.3` now with the verification note, leaving the parent epic alone.

The phase bead is closed. I’m doing one last state check now: bead status and the changed files in the main and linked core repos, so the final declaration has the right shape.

Everything is closed and the modified-file set is exactly the retention work in main plus the Rust core file. I’m reading the finalizer instructions once more, then the SASE final declaration will be my last tool action before the final reply.

Finalizer instructions loaded. I’m fetching the host’s final context now so I can declare the repository commits correctly.

The final context has two repository obligations: main and linked `sase-core`, both written by this run. I’m submitting commit decisions now: `close` on the primary main-repo decision, `keep` on the linked core repo decision. This is the final tool action if it succeeds.

The final submit rejected the `close` bead action because it couldn’t read the assigned bead status, so the successful-submit “last action” hasn’t happened yet. I’m refreshing the final context and checking that validation path; likely the right recovery is to commit with `keep` because the bead was already explicitly closed as requested.

The refreshed context is unchanged. Since the bead is already closed by the explicit `sase bead close` the user asked for, I’m resubmitting the repository commits with `bead_action: keep` so the finalizer commits the work without trying to close the bead a second time. This is the final tool action if it succeeds.

Completed and closed `sase-zw.8.7.3`.

Implemented the run-retention safety work across main and `sase-core`: schema v2 protection inputs, symlink/invalid-path rejection, apply-time revalidation, protected empty-run preservation, safe empty-shard cleanup with preview/apply budget parity, and deduplicated actionable Axe preview notifications.

Verified:
- `cargo test -p sase_core agent_artifact_run_retention`
- `just rust-install` into the workspace venv
- focused pytest for retention bindings and Axe notification contract
- linked core `just check` with `LD_LIBRARY_PATH`
- main `just check` with `LD_LIBRARY_PATH`, including escalated full suite

Also ran `sase bead epic-symbols sase-zw.8.7.3`: no leftovers. Final declaration was accepted for the repository commits. One unrelated transient full-suite failure was recorded as a `PROPOSED FOLLOW-UP` note after it passed on rerun.
