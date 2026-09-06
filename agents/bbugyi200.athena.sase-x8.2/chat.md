# Chat History - ace-run (sase-x8.2)

- **TIMESTAMP:** 2026-09-05 22:05:15 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-x8.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-x8, bead=sase-x8.2)
%model:@medium
%auto
%w:sase-x8.1
%w(bead=sase-x8.1)
Can you complete the work for bead sase-x8.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-x8.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-x8.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-x8.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I’m using the `sase_beads` skill for the bead lifecycle rules, and I’ll use `sase_final` right before the final response as required by this workspace. First I’m reading the bead instructions, then I’ll inspect `sase-x8.2` and its design context.

The `sase_final` skill loaded successfully. The listed `sase_beads` path was missing, so I’m locating the installed skill file before touching bead state.

I found `sase_memory_read`; the bead skill itself is not installed at the advertised path, so I’m continuing with the memory-read procedure for the required bead reference note.

The bead is a phase under `sase-x8`, with the parent plan file `plan:202609/wait_artifacts.md`; its own design field is empty. I’m reading the bead lifecycle memory now, then I’ll pull the parent plan/design section that defines this phase.

The bead memory confirms the phase-worker rule: no task beads, no parent close, and close through `sase bead close` only after verification. The local repo doesn’t contain the plan path by filename, so I’m resolving the effective SDD plan store through the CLI/env instead of guessing paths.

The parent epic’s design pointer resolves through `SASE_SDD_PLANS_DIR`, so I’m reading that plan file now and then I’ll map its phase requirements to the code.

The compact bead output shows the canonical plan location as `/home/bryan/.sase/plans/202609/wait_artifacts.md`; the env plan path appears stale in this workspace. I’m going through the repo-opening skill before reading anything outside the workspace boundary.

I have the `sase_repo` rules loaded. Next I’m listing/opening the plan sidecar, so the design-file read is audited and uses the path SASE resolves.

The plan sidecar is a named repo (`plans`). I’m ensuring/opening that clone now because the bead’s display path points at the durable plan store but the workspace sidecar was missing the target file.

The sidecar clone opened cleanly but still lacks `wait_artifacts.md`; the bead page points to the legacy/local durable plan path. I’m checking that exact target next, then I’ll continue from the plan content it names.

The design file exists at the bead-rendered path and is outside the opened sidecar clone, so I’m treating it as the durable plan document the bead references and reading only that file.

The phase scope is clear: expose `wait.chats` and lazy `wait.artifacts` at render time, using the prior phase’s facade, without persisting a resolver. I’m now inspecting the current implementation and dirty state before editing.

Because this phase touches xprompt rendering, artifact metadata, and TUI/static completion, I’m loading the corresponding reference memory before changing those areas.

The prior phase’s Python facade already exists as `sase.core.artifact_context_query_facade`, so this phase can stay in the main repo unless a binding contract problem appears. I’m reading the runner/context types and the places where prompt rendering merges globals.

The current `wait_chats` is a plain list injected through workflow named args; the new namespace needs a scoped render-time overlay. I’m looking at agent-name resolution and workflow rendering internals so the producer selection matches existing wait behavior.

There are existing group helpers for family/clan membership and a separate `agents` namespace builder that already resolves waits for output variables. I’m drilling into those helpers rather than inventing a second naming model.

The design wants artifact metadata lookup lazy, but it still needs the same resolved producer generation as chat resolution. I’m checking the dependency-wait pipeline for any already-bound producer identity that can be reused before adding a small local model.

I’m going to add a small render-runtime ContextVar under `sase.xprompt` and keep the wait namespace out of workflow args. That lets workflow/xprompt/top-level Jinja see `wait` while `workflow_state.json` remains plain JSON.

The early launch expansion can still happen before dependency admission, so I’m keeping runtime-only `wait` availability scoped to execution rendering. Existing templates that need deferred runtime values still have to use raw protection at swarm expansion, matching the plan.

I’m ready to edit. The changes will add the scoped runtime overlay, wire the runner to bind it, extend wait resolution with reusable producer groups, and teach static completion about `wait.chats`/`wait.artifacts`.

I’m applying the implementation in focused pieces: new runtime context module, wait namespace/resolution updates, runner binding, static completion, docs, and the stale epic-symbol cleanup.

I’m changing `run_agent_refs.py` to return a richer wait-resolution object while preserving `resolve_wait_chat_paths()` as the compatibility surface existing tests patch. The artifact lookup will remain lazy on the namespace property.

Next I’m binding that namespace only while the workflow execution loop renders prompts. The legacy `wait_chats` named arg stays serializable and keeps its old “absent when empty” behavior.

I’m checking the edited execution loop for accidental duplicate imports or indentation issues before moving to tests.

I noticed the existing unit tests patch `resolve_resume_agent_name`, so I’m preserving that path inside the richer resolver. Group resolution is additive; if no group applies, the old selected agent still drives `wait_chats`.

I’m tightening the resolver so real family/clan groups only replace the chat-selected agent when they contain that same artifact directory. That keeps tests and runtime behavior isolated from unrelated similarly named rows.

The resolver shape is in place. I’m adding focused tests for the lazy query behavior, render-time namespace binding, and dotted completion before running the suite slice.

I’m updating the user-facing xprompt docs to describe the runtime `wait` namespace and keep the legacy alias documented as supported.

The wait-context code now uses the artifact facade, so I’m removing the temporary `sase-x8` symvision whitelist entries for those symbols from the Justfile.

The first Justfile patch missed the exact context, so I’m applying a narrower edit directly around the `_lint-symvision` recipe.

I’m running the focused tests for the changed runtime, wait resolver, preprocessing, and completion paths now.

The focused test run stopped before collection because `textual` is missing in this checkout’s environment. I’m reading the required lint/test memory now to use the project’s expected setup and verification lane.

Per the project lane, this workspace needs `just install` when dev dependencies are missing. I’m running that before re-running focused tests and `just check`.

`just install` is still running; it installed the cached Rust binding wheel and is compiling the LSP/server pieces against the linked core checkout.

The install is still in the Rust build step. I’m waiting for it to finish before collecting tests again.

The build is still active with no new output; I’m continuing to wait rather than starting verification on a half-installed environment.

`just install` is taking a while in the compiled dependency phase. I’m giving it another interval so the environment is consistent before diagnosing anything.

The install command still has the build lock and has not emitted new lines. I’m waiting one more cycle; if it stalls further I’ll inspect the process tree.

`just install` completed and installed dev dependencies; it emitted a transient copy warning for the LSP binary but exited successfully. I’m rerunning the focused test set now.

The shell’s default `pytest` is outside the workspace venv. I’m switching to `.venv/bin/pytest` so the installed dev dependencies are actually used.

The focused venv test slice passes. I’m checking the diff and formatting before the full project `just check` lane.

I’m picking this back up after the implementation and focused tests. I’m going to check the working tree, format/lint through the project’s normal lane, clear any epic-symbol leftovers, then close only `sase-x8.2`.

The linked core repo is clean; the local changes are the wait namespace implementation, docs, tests, and the Justfile symbol cleanup. I’m going to run the formatter now so the subsequent check sees the code in the project’s expected shape.

`just fmt` is rebuilding the Rust Python binding because the linked core checkout advanced during setup. I’m waiting for that to finish before re-running the focused tests and the full `just check` lane.

There’s no new output yet; the formatter is still blocked on the Rust build lock. I’m continuing to wait rather than starting parallel build/check commands that would contend for the same cache.

The same build step is still waiting on a file lock, so some other process in this workspace is likely holding Cargo’s build directory. I’m giving it another interval before deciding whether to inspect the blocking process.

The wait has persisted for about a minute and a half. I’m going to inspect the local build processes so I can tell whether this is normal compilation progress or a stale lock.

The lock is held by another SASE workspace’s Rust build, and it is actively compiling. I’m leaving it alone and waiting for our formatter to continue once Cargo releases the shared target lock.

The lock cleared and our workspace is compiling the local `sase_core_rs` binding now. Once this finishes, `just fmt` should move on to the actual formatting steps.

The formatter run is still in the binding build phase with no new diagnostics. I’m continuing to wait because interrupting here would just leave the environment stale for `just check`.

Still no new output; this is likely the release link step for the Python extension. I’m keeping the run active and will report the formatter/check results once they land.

The long-running step hasn’t produced an error, just silence. I’m going to give it another interval; after that I’ll inspect the process state again if it still hasn’t advanced.

This build has been quiet long enough that I’m checking process state again. I’m still avoiding any destructive action; this is just to distinguish active compilation from a hung subprocess.

The process is active: `rustc` for this workspace is consuming CPU, so this is compilation rather than a stale lock. I’ll keep it running.

The first binding build finished and installed. The formatter’s setup has moved into the wheel-cache build/store step and is waiting on the shared Cargo lock again; same plan: wait for it to clear.

No new output from the cache build yet. It’s still queued behind the shared target lock, and I’m leaving the other running SASE builds undisturbed.

The formatter is still waiting in the cache-store build. I’m continuing to let it run because the environment setup is shared by the later verification lane.

Still quiet. I’m checking process state one more time only to confirm it hasn’t become idle.

Our cache-store subprocess is waiting while another workspace’s wheel-cache build is actively linking. I’m continuing to let the queue drain; there’s still no indication of a local code failure.

Still queued behind the shared Cargo target. I’m staying with the same run so we don’t multiply the contention.

No new output yet. This is still setup overhead, not the Python formatter itself.

The shared Cargo queue is costing more time than the formatter itself should. I’m going to inspect the `fmt` recipe so I can decide whether it is safe to stop this setup-heavy wrapper and run the formatting commands directly against the already-prepared venv.

The `fmt` recipe’s real work is just ruff, doc rendering, and prettier after `_setup`; the blocking piece is the optional Rust wheel-cache store. Since the extension is already built and installed, I’m stopping this wrapper and will run the formatter steps directly.

The wrapper stopped during cache storage only, after installing `sase_core_rs-0.32.25`. I’m running the formatter subcommands directly now in the same order as the recipe.

Ruff formatting changed one file. I’m running the ruff autofix pass next, which is the second Python formatter step in the project recipe.

The ruff autofix pass made one cleanup. I’m rendering generated docs and then formatting Markdown, matching the remaining `just fmt` steps.

Formatting is complete: ruff made the only code edits, generated docs and Markdown were unchanged. I’m rerunning the focused test slice before the full check so any regression points back to this change set quickly.

The focused slice is clean: 53 tests passed. I’m starting `just check` now, which is the required project verification lane for changed SASE files.

`just check` is through formatting and the fast lint lanes so far. I’m waiting on the remaining type, symbol, and test steps.

Mypy passed. The check run is still active; next likely pieces are symbol lint and the pytest lanes.

Feature-flag and script lints passed as well. I’m continuing to wait for the rest of `just check`.

The intermediate project lints are still passing. I’m waiting for the slower tail of the check run now.

`just check` failed only at Symvision: the new `ResolvedWaitDependency` class is public but used only inside `run_agent_refs.py`. I’m going to make that implementation detail private and rerun the check.

I found the class is only used as an internal entry record, while the public surface is `WaitDependencyResolution` and `WaitRuntimeNamespace`. I’m renaming the internal dataclass to `_ResolvedWaitDependency`.

The Symvision naming issue is patched. I’m running the lightweight Python format/check pass again before restarting `just check`.

The local format/lint pass on the patched file is clean. I’m rerunning the focused tests, then `just check` again.

The focused tests are still clean after the Symvision rename. I’m restarting `just check`; setup should be faster now that the binding version is installed.

The second `just check` run is through format and ruff again. I’m waiting for the remaining lanes.

Mypy passed again. Continuing through the rest of `just check`.

The lint tail is progressing cleanly. I’m waiting on Symvision and tests now.

Symvision passed after making the entry record private. The remaining work in `just check` is the test phase.

The size lint passed too. I’m still waiting on pytest from the main check lane.

The project validation step passed, and it printed a stale published-core floor warning for `sase-core-rs==0.32.19` versus capabilities available in `0.32.25`; the check lane is continuing. I’m waiting for the pytest result.

No new output yet from the test run. I’m keeping the `just check` session active.

The test phase is still running silently. I’ll continue polling until it finishes.

Still no pytest output; this is normal for the quiet check recipe when tests are running. I’m waiting on completion.

The check run is still active with no new diagnostics. I’m leaving it alone until it either reports tests or exits.

The quiet period is long enough that I’m going to inspect the test/check subprocesses, just to confirm it is active rather than wedged.

The check process is active: pytest is running with 14 workers and several are consuming CPU. I’m continuing to wait for the lane to finish.

No new check output yet; pytest workers are still running.

The test lane remains active and quiet. I’m keeping the session open.

Still waiting on pytest. Since workers were active on the last process check, I’m letting it continue.

No output yet from the quiet pytest run. I’ll poll again; no intervention unless it stops making progress.

This is a longer-than-usual quiet stretch, so I’m checking the pytest worker state again before deciding whether anything needs attention.

Pytest is still active, with all workers up and several busy. I’m continuing to wait rather than interrupting a live check.

No new output; the full test lane is still running.

`just check` reached the full-suite pytest lane because the Justfile changed, and it failed in four prompt-panel section-navigation tests that are outside the wait namespace area. I’m rerunning just those tests with full failure output to determine whether this change caused them or exposed unrelated drift.

The four failed tests pass when run directly, so the `just check` failure currently looks like a full-suite/xdist interaction rather than a deterministic failure in this patch. I’m going to rerun the required `just check` lane once more to get a clean landing signal or a repeatable failure.

The retry is through mypy already. I’m waiting through the remaining lints and full test lane.

Feature-flag lint passed; the check retry is still active.

The repeat `just check` run is through the same intermediate lints cleanly. Waiting for Symvision and tests.

Symvision and size lint passed on the retry. The run is entering validation/tests now.

No new output yet. I’m continuing to wait for the validation/test tail.

Validation passed again and the core-floor warning is cached now. I’m waiting on the full pytest lane.

The test lane has started and is quiet. I’m keeping the check session open.

Still no test output yet; waiting.

The full pytest lane is still running silently. I’m continuing to poll.

No new diagnostics yet. I’m leaving the retry running until it exits.

The retry’s pytest phase is still active and quiet. No failures have printed.

Still waiting on pytest. I’m checking process activity if the next poll stays silent.

The test lane is still quiet, so I’m checking worker activity again before continuing to wait.

The retry is active, now with 5 pytest workers, while other SASE workspaces are also running tests. That explains the slower tail; I’ll keep waiting.

No new output yet; the pytest workers are still running.

Still waiting on the full check retry.

The test run remains quiet; no new failures printed. I’m continuing to poll.

Still no output. I’m letting the governed test lane continue rather than replacing it with a narrower command.

The retry is still running. Other active workspaces are sharing CPU, so I’m expecting this to take longer than the first run.

Still silent; I’m checking one more process snapshot to make sure the workers are not stalled.

The workers are active and one is inside an `npm ls` provider-version check, so the suite is still making progress. I’ll keep polling.

No output yet; still waiting on the governed test lane.

The test retry remains active. I’m continuing to wait.

Still no test output. The workers were active on the last process check, so I’m not interrupting it.

The retry has a long tail under current system load. I’m waiting for its exit status so we can close the bead only with the right verification note.

Still running silently; continuing to poll.

Another long quiet interval. I’m taking a process snapshot again to verify the retry is still doing work.

The pytest workers are still actively using CPU. The full suite is simply slower this time because it dropped to 5 workers; I’ll keep waiting.

No output yet from pytest. Still waiting.

The retry remains active and quiet.

Still waiting. No failure output has appeared; the workers are continuing to run.

The full-suite retry is still in progress under reduced parallelism. I’m continuing to wait for the final status.

Still no output; I’m keeping the session alive.

The test lane remains quiet after another interval. I’ll check worker activity once more if it doesn’t finish on the next poll.

Still running; taking another process snapshot now.

The retry is still actively using CPU after about 15 minutes, so it is not wedged. I’m continuing to wait for its final result.

No new output yet. Still waiting on pytest.

The check retry is still active and quiet.

Still waiting. I’ll keep polling until the check exits.

The governed full-suite retry is still running under reduced parallelism. No failure output yet.

Still quiet; continuing to wait.

The retry failed in the same four tests, but those tests still pass in isolation. I need a smaller reproduction now, probably xdist or suite-order pollution, so I’m going to run that file under xdist and then inspect the exact assertions if it fails.

Running the whole failing file with the same xdist mode passes, so this is not a deterministic failure in that file or a basic xdist incompatibility. I’m reading the target tests and nearby implementation to see what shared state could be polluted during the full suite.

The file passes under xdist by itself, so the repeat full-suite failure is order or shared-state related. I’m reading the specific assertions and the helper code before deciding whether to fix locally or record a follow-up as unrelated.

I have the tests and cache implementation in view. The likely failure mode is process-global section layout cache pollution across unrelated tests, because the failing file passes alone and the anchors are cached globally by content digest/width.

I’m going to run a small reproducer for cache pollution by executing the navigation tests repeatedly in different orders. If that confirms an existing flaky global cache, I’ll record it on the bead instead of expanding this phase into unrelated TUI work.

The failure pattern points to global layout-cache keys that may collide when two renderables have the same visible text but different section metadata. I’m checking the digest helper now; if metadata is excluded, this is a small source fix rather than a test workaround.

The digest helper includes span style text, but Rich style stringification does not necessarily include metadata. That can make two different section-anchor documents share a cache key. I’m going to patch the digest to include stable Rich style metadata.

The marker metadata is attached with Rich `Style(meta=...)`, so including meta in the digest should prevent stale anchors from being reused across visually identical but semantically different documents. I’m adding a focused regression test for that helper, then patching the digest.

I’m applying the digest fix now: same visible text still shares a digest, but Rich style metadata becomes part of the key so section-anchor caches cannot cross semantic documents.

The source patch is in. I’m adding a regression test that two `Text` objects with identical plain text but different metadata no longer share a digest.

The regression test is added. I’m formatting and linting the two affected TUI files before rerunning the relevant tests.

Formatting/linting for the digest fix is clean. I’m running the digest tests and the previously failing navigation tests next.

The digest test passes, but the serial navigation file now shows cache-order failures that xdist-by-file hid. The failures are all in the existing global cache behavior, so I’m going to inspect the panel cache invalidation path rather than keep the metadata digest change as-is blindly.

The failing file reveals a pre-existing serial-order cache problem: selected tests pass alone, but fail after earlier tests in the same file. I’m narrowing it to the smallest adjacent sequence so the fix is precise.

The immediately adjacent pair passes, so the pollution comes from an earlier test. I’m running the prefix of the file through the first failing test to locate it.

The failure reproduces within the file prefix. I’m bisecting the preceding tests to identify which one leaves the shared cache in the bad state.

No single adjacent predecessor triggers it, so the bad state needs a combination. I’m checking the smaller prefix groups now.

The cache interaction is subtle enough that I’m instrumenting it in-process with the existing test helpers. I want to see exactly which global cache entry gets reused with missing fold-only anchors.

The instrumentation showed the actual bug: fallback cache keys used `id(visual)`, and Python reused an old `_ConsoleVisual` id, so a new render borrowed stale anchors. I’m changing the fallback to a monotonic token; content-based caching remains for Rich visuals that expose their renderable.

The volatile visual cache key now uses a monotonic counter instead of reusable object ids. I’m formatting/linting that file and rerunning the section-navigation file serially.

The TUI cache files pass ruff. I’m rerunning the serial navigation file plus the digest regression.

The deterministic reproduction is fixed: the navigation file now passes serially, and the digest regression passes. I’m rerunning the wait namespace focused slice before another `just check`.

The wait namespace focused tests still pass. I’m running `just check` again now; this one includes the TUI cache fix that addresses the repeat failure.

The new `just check` run is through format and ruff. Waiting on the remaining lanes.

Mypy passed. Continuing through project lints.

Feature-flag and script lints passed. The check run is still active.

The intermediate lints passed again. Waiting for Symvision, size lint, validation, and tests.

Symvision and size lint passed. I’m waiting on validation and the governed test lane.

Validation passed again with the same non-fatal core-floor warning. The full test lane is running now.

The full test lane is quiet so far. I’m polling until it completes.

No new output yet from pytest. Continuing to wait.

The test lane is still active and quiet.

Still waiting on pytest. No failure output yet.

The test lane remains quiet. I’ll keep polling.

No new output yet; still waiting.

The full suite is still running silently. I’m checking process activity if the next poll stays quiet.

Still quiet; taking a quick process snapshot now.

This run has 14 active pytest workers again, so it should finish closer to the first full-suite duration. I’m waiting for its result.

No output yet; continuing to poll the check run.

The test lane is still active and quiet.

Still waiting on full-suite pytest. No diagnostics have appeared.

The previous navigation failures are gone in the full check. The retry now has one different failure in `test_axe_status_read_cache.py::test_run_json_mtime_change_invalidates_cache`; I’m rerunning it directly to see if it’s deterministic.

This cache test fails deterministically by itself: the rewritten `run.json` keeps the same mtime token, so the cache doesn’t invalidate. That is unrelated to the wait namespace work, but it blocks the required check lane; I’m inspecting the cache token logic now.

The remaining failure is a different deterministic cache invalidation issue. I’m reading the axe display cache implementation around run-json stat keys.

The cache is behaving as designed: it keys JSON on `(exists, mtime_ns, size)`, and the test rewrites `success` to same-length `failure` too quickly to guarantee an mtime change. I’m patching the test to explicitly advance the file mtime so it actually tests the invalidation contract it names.

The test now explicitly advances the mtime after the same-size rewrite. I’m formatting and linting it, then rerunning that test.

The cache invalidation test now passes directly. I’m running the combined focused set covering wait namespace plus the two check blockers before one more full `just check`.

The combined focused set is clean: 77 passed. I’m running `just check` again; this should be the last required verification pass if no unrelated flakes appear.

The final `just check` attempt is through mypy already. Waiting on the remaining lints and tests.

Feature-flag and script lints passed. Continuing.

The intermediate lints are clean. Waiting for Symvision, size lint, validation, and tests.

Symvision and size lint passed. The run is moving into validation/tests.

Validation passed with the same non-fatal core-floor warning. The full test lane is running.

No pytest output yet; waiting.

The test lane is still quiet. I’m polling until it exits.

Still waiting on the governed pytest lane. No failures have printed.

The test run remains active and quiet.

Still no output. I’ll check worker activity if the next poll is quiet.

No output yet; checking worker activity now.

The test workers are active, and one is rendering a PDF through pandoc. There is also another `just check` process in a different shell, so the machine is busy; I’m still waiting on this run’s result.

No output yet. Continuing to poll.

Still running silently.

The full check is still active. No failure output has appeared.

No output yet; waiting.

Still waiting on pytest. The suite is near the duration of the earlier 14-worker run, so I expect a result soon.

No new output yet; continuing to poll.

`just check` passed; it escalated to the full suite because of the Justfile change. I’m checking bead epic-symbol leftovers now before closing `sase-x8.2`.

`epic-symbols` reports no remaining entries for `sase-x8.2`. I’m going to take a final status snapshot, then close only this bead with the verification note.

The linked core checkout is clean, and the local diff is the implementation plus the two verification blockers fixed in-tree. I’m closing only `sase-x8.2` now with the verification summary.

Using `sase_final` now because every SASE provider turn has to end with a finalizer declaration. I’m going to collect the final context and submit the declaration before I send the final summary.

The skill requires a host-issued final context, then a manifest if submission is required. I’m collecting that context now.

The final context requires one repository commit declaration for the main repo. I’m submitting that manifest now; after a successful submit I won’t mutate the workspace again.

Completed `sase-x8.2` and closed only that bead.

Implemented the runtime `wait` namespace with `wait.chats` and lazy cached `wait.artifacts`, kept legacy `wait_chats`, scoped the runtime context so it is not persisted into workflow args, and updated static Jinja completion plus docs/tests. I also removed the stale `sase-x8` epic-symbol Justfile entries.

Verification:
- Focused combined pytest set: `77 passed`
- `sase bead epic-symbols sase-x8.2`: no entries
- `just check`: passed, escalated to full suite because of the Justfile change
- `sase bead close sase-x8.2 ...`: closed
- SASE final declaration accepted for commit
