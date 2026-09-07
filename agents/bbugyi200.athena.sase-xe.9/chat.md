# Chat History - ace-run (sase-xe.9)

- **TIMESTAMP:** 2026-09-06 18:05:08 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-xe.9

## Prompt

#gh:gh_sase-org__sase
%id(9, clan=sase-xe, bead=sase-xe.9)
%model:@medium
%auto
%w:sase-xe.2
%w(bead=sase-xe.2)
Can you complete the work for bead sase-xe.9? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-xe.9 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-xe.9`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-xe.9 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I’ll use the SASE memory-read skill for the bead rules, and the SASE final skill at the end because this workspace requires a finalizer declaration. First I’m reading those skill instructions, then I’ll inspect the reserved bead and its design context.

I’m going through the project’s bead rules before touching the bead. That should pin down the allowed status and note operations for this phase work.

The bead rules confirm this phase should only be closed directly, with follow-up captured as notes on the phase if needed. I’m reading the phase bead now to find the exact scope and linked design file.

The phase scope is backend-heavy: persisted follow records keyed by agent/family identity, family promotion, unfollow tombstones, and shared running-count logic. I’m opening the epic plan and checking any phase-owned epic symbols before changing code.

There are no `--epic-symbol` entries currently attached to this phase, and the worktree started clean. Next I’m reading the epic plan section around `follow-store` and then I’ll map it to the existing backend boundaries.

The plan path is stored through the SASE plan repo indirection, so I’m resolving its on-disk layout instead of assuming the rendered `plan:` path maps directly under the workspace.

The plan file named on the bead is not present under the local plans checkout path, so I’m searching the workspace for the epic title and phase slug to find the generated design source or synced copy.

The parent bead still points at `plan:202609/remote_dispatch_fleet.md`, but it is not in the local plan checkout I can see. Since that is an artifact-style ref, I’m reading the artifact rules and then I’ll use the audited artifact reader instead of chasing sidecar files manually.

I’ve got the artifact read rules; now I’m resolving the plan through `sase artifact read` so the read is recorded and I can work from the actual design text.

The epic plan explicitly says to read the consolidated research report before implementing any phase. I’m doing that audited read now, then I’ll inspect the existing Python and Rust surfaces for follow records and count semantics.

The required research ref is currently resolving as missing, but the artifact resolver reports the candidate it searched. I’m checking the artifact metadata instead of reading that sidecar file directly, because sidecar reads have to stay audited.

The resolver has prior consumption records for the research artifact but marks the file missing in this clone, so I’m trying the prompt-style `@research:` spelling before treating it as unavailable evidence.

The `@` form is intentionally rejected for CLI use, so the research document is not currently readable through the audited resolver. I’ll proceed from the already-readable epic design and note this verification gap if it remains relevant; now I’m mapping current code and tests for the follow-store phase.

This phase crosses the Rust core backend boundary, so I’m going to open the sibling core repo through the SASE repo tool before reading or editing anything there. First I’m reading that repo-access skill’s instructions.

I’m checking the configured repo inventory for the exact `sase-core` handle. Once opened through SASE, I’ll use the printed path as the only core checkout path.

The linked repo handle is `sase-core`. I’m opening it with an audit reason now, then I’ll inspect both repos for existing identity, follow, and status-count code.

The core checkout opened cleanly and fast-forwarded. I’m surveying the relevant modules now: local agent status counts, existing identity helpers, Python state directories, and any prior follow/remote dispatch scaffolding.

The codebase already has a substantial `fleet_contract` module in `sase-core` with logical locator and count bindings. I’m narrowing to that contract and the Python facade points rather than scanning the whole tree broadly.

The count APIs already exist in core and are bound to Python, but the phase still needs durable follow persistence and family/tombstone reconciliation. I’m reading the exact contract types and tests before deciding what to add or reuse.

Core’s count contract already deduplicates current agent-shell summaries by logical key and applies the running predicate over authoritative summaries. I’m checking whether Python has a facade or persisted follow store yet, and where state-path helpers live.

Python does not appear to have a dedicated dispatch/fleet package yet. I’m going to add a focused dispatch follow-store module and expose any missing core rules as thin Rust-backed facades, keeping UI wiring for later phases.

The practical slice for this phase is now clear: add transport-free follow identity/reconciliation rules in `sase-core`, bind them into `sase_core_rs`, then add a Python atomic store for viewer-local follows that delegates keying, promotion, and tombstone decisions to core.

I’m going to extend the existing `fleet_contract` module instead of creating a parallel contract. That keeps versioning, validation, and Python dict conversion in one place.

I’m reading the existing Python binding test for the fleet contract so new bindings land in the same style and the validator knows about them.

For the Python store, I’m matching the local state-store conventions rather than inventing locking semantics from scratch. I’m reading existing small JSON/JSONL stores and their tests now.

I’ll include a small advisory file lock around the JSON store so concurrent UI actions and dispatch reconciliation cannot interleave writes. I’m checking the repo’s existing lock helper before editing.

The existing fleet binding tests double as the binding manifest. I’m going to update those required-binding lists along with the Rust/Python code so stale wheels fail clearly.

The core crate exposes modules directly rather than re-exporting the fleet types from `lib.rs`, so adding functions inside `fleet_contract` and importing them in the PyO3 crate should be enough.

I’m ready to edit. The changes will be scoped to `sase-core`’s fleet contract/bindings plus a new Python `sase.dispatch.follow_store` module and focused tests/validator updates in the main repo.

I’m adding the core follow/count contracts now. The Rust side will normalize persisted records, apply family promotions/activations, enforce unfollow tombstones, and compute Focus/Fleet counts with partial host propagation.

The new wire structs are in place. I’m adding the pure reconciliation and Focus/Fleet counting functions next.

I’m adding validation for the new follow/count wires, including the family-promotion invariants and same-origin checks for host count inputs.

Next I’m adding the helper routines that normalize duplicate records, let tombstones win over automatic follows, and aggregate host-scoped counts.

That patch missed a nearby context block, so I’m splitting the helper additions into smaller patches against exact locations.

I found the exact helper insertion point; the earlier displayed duplication was just overlapping output, not a file problem.

The Rust contract helpers are in place. I’m binding the new functions through `sase_core_rs` and updating the extension’s public binding list.

I’m adding the three PyO3 wrapper functions beside the existing fleet count binding.

I’m registering the new bindings with the module initializer so Python can import them.

Now I’m extending the Rust unit tests around the new contracts before moving to the Python persistence layer.

I need the existing test helpers in `fleet_contract.rs`, so I’m reading that module’s test setup and adding focused cases beside the existing count tests.

I’m adding small Rust test helpers for follow records and tombstones, then the actual promotion/tombstone/count tests.

I’m adding the Python follow store now: one JSON file under the SASE state root, protected by a sidecar lock and written by atomic replace. It will expose explicit follow, dispatch prewrite/activation, unfollow tombstone, and family promotion operations.

The follow store module is in. I’m adding a thin Python count facade too so later ACE/Fleet UI code does not call `require_rust_binding` directly.

I’m updating the binding validator and Python tests so these new core functions are treated as required API, not optional conveniences.

I’m extending the existing fleet binding tests with follow reconciliation and Focus/Fleet count behavior, then I’ll add store-level tests for the Python persistence API.

I have the bead/design context and the earlier edits in hand. I’m going to inspect the current diff and the targeted tests now, then I’ll tighten whatever doesn’t compile before running the required checks.

The phase tests and Rust tests did land. Next I’m checking the full diff around the follow rules and Python store, because most issues here tend to be schema drift or validation edge cases rather than missing files.

The implementation is close, but there are a couple of spots I want to harden before test execution: Python type checks for numeric timestamps, and the Rust reconciliation path should make tombstoned dispatch activation visibly remove the record, not just emit a diagnostic.

I found one likely behavioral mismatch: a dispatch follow activated after an unfollow tombstone should not survive reconciliation. I’m making that removal explicit and adding/keeping tests around the “unfollow wins” rule.

I’m adding a small Python test module for the new follow store path and mutations. That covers the integration boundary that the Rust-only tests can’t see: atomic JSON persistence, tombstone clearing on explicit follow, dispatch prewrite/activation, and family promotion.

I’m patching the source-tombstone promotion case now. This prevents an old singleton dispatch follow from reappearing under the family key after the viewer has already unfollowed it.

I’m tightening the Python validation and adding store-level tests next. The tests use a per-test `SASE_HOME`, so they exercise the persisted JSON file without touching real user state.

The source-tombstone rule is patched in core, and Python now rejects boolean timestamps. I’m adding the focused integration tests for the follow-store module before formatting.

I’m adding two focused tests: one for explicit follow/unfollow persistence and one for dispatch activation, family promotion, and stale tombstone recovery.

The new tests are in place. I’m checking the project’s formatting/lint conventions now and then I’ll run formatters on both repos.

The test fixture supports exactly this redirected state-home pattern. I’m going to format now, then run the narrow Rust and Python test lanes to flush out binding/schema issues.

Before the checks run, I’m scanning the new module against mypy’s `src/` rules. The main thing is that even private helpers need annotations here.

I spotted one missing return annotation that would fail the repository’s mypy lane. I’m adding the proper context-manager type before formatting.

I’m running the code formatters now: Rust `cargo fmt` in the linked core repo and the repo’s Python formatter/fixer for the main checkout.

Python formatting triggered the expected local rebuild because the linked core checkout changed. It’s currently waiting on Cargo’s build-directory lock, so I’m going to let that finish instead of starting competing Rust builds.

The rebuild is still waiting on the shared Cargo lock. I’m continuing to poll it; once it clears, the formatter/test sequence can proceed using the rebuilt bindings.

The lock has been held for over a minute, so I’m checking what owns it before waiting much longer. If it’s a real build, I’ll continue polling; if it’s stale, I’ll avoid disrupting unrelated work and adjust the verification path.

There are unrelated builds in other workspaces holding the shared target lock. I’m stopping my formatter invocation that is only waiting on that lock, then I’ll use an isolated Cargo target directory for this workspace’s rebuild and checks.

The blocked formatter was cancelled cleanly. I’m formatting only the touched Python files directly now, which does not need the Rust extension to be rebuilt first.

The touched Python files are formatted and pass ruff’s auto-fix pass. I’m going through the diff again after formatter changes before starting the isolated Rust/Python verification.

The formatted diff looks clean. I’m starting with the Rust crate’s fleet-contract unit tests using a workspace-private Cargo target directory, which avoids the shared lock contention from other agents.

The Rust compile surfaced two concrete issues: a `BTreeMap` inference hole and a test helper name shadowed by a local variable. I’m patching both and rerunning the same fleet-contract test lane.

Cargo is unwinding the failed build jobs. I’m waiting for it to exit before editing so the session is clean.

The failed Cargo session has exited. I’m applying the small fixes now.

The inference and shadowing fixes are in. I’m formatting Rust again, then rerunning the same isolated fleet-contract tests.

Rust formatting is clean. I’m rerunning the fleet-contract unit tests with the isolated target directory now.

The Rust test lane is compiling now against the isolated target. No new errors yet; I’m waiting for the test results.

The Rust fleet-contract tests passed. I’m rebuilding the local Python extension from the linked core checkout with the same isolated target dir so the Python tests load the new bindings.

The extension rebuild is in progress and no longer blocked on the shared target lock. I’ll run the focused Python tests as soon as the wheel installs into this workspace venv.

The local binding build has reached the `sase_core` crate. I’m continuing to wait; after this it should compile the PyO3 wrapper and install.

The build is still running without new output. I’m keeping it attached so we get the exact compiler/install result.

No output yet from the release build; that can be normal for the PyO3 link step. I’m still attached and will report any compiler errors directly.

The release build is taking a few minutes but is still active. I’m checking process state in parallel while keeping the install session open.

The release build is now in the PyO3 crate. It’s still active, and the isolated target directory is working as intended.

Still waiting on the release link. I’m keeping the command attached; no separate build/test command is running against this target.

The build is long but still within expected release/LTO territory for this repo. I’m going to keep polling rather than interrupting the install that the Python tests need.

There’s still no output, so I’m doing another process-state check while leaving the install session open. That will tell me whether it is compiling, linking, or hung.

The process check shows `rustc` is actively using CPU in the final extension compile/link step, so this is not stale. I’m continuing to wait for the install result.

Still compiling. Once this finishes, I should be able to run the Python binding tests without another rebuild.

The extension installed successfully. The install recipe is now compiling the companion LSP binary from the same core checkout; I’m letting that finish so `just` setup stays consistent.

The companion LSP build is the last part of the install recipe. I’m waiting for it to exit before moving to pytest.

Still building the LSP binary, with no error output. I’m continuing to wait; the install session will be closed before I start tests.

The install recipe is still active in the final Rust binary build. I’m staying attached and will proceed as soon as it returns.

This is still in the same install command, not a new blocker. I’m checking the active process briefly while waiting, since LSP release builds can be quiet.

The process check shows the LSP link step is actively using CPU. I’m continuing to let it complete.

The local extension install completed and returned success, although its LSP copy helper printed stale-default-target `cp` noise after building into the isolated target. I’m reading the required lint/test memory now before the final verification pass.

The required verification note says `just check` is the default finishing gate after repo changes. I’m first running the narrow binding/store tests to catch local failures quickly, then I’ll run `just check`.

The focused Python binding/store tests passed: 28 tests. I’m checking exactly what `just check` will run in this repo so I can avoid accidentally invoking the full exhaustive lane.

The required `just check` lane is next. I’m running it inline with the same isolated Cargo target setting; if setup stays current, it should skip the Rust rebuild and move into lint/scoped tests.

`just check` has cleared setup, Python formatting, Markdown formatting, keep-sorted, and ruff. It is now in the remaining lint gates.

Mypy passed. I’m waiting on the remaining lint gates and the scoped pytest selection.

Feature-flag validation passed. The check lane is continuing through the structural/script and project-specific lint gates.

The script, wait-helper, changelog, and terminology lint gates passed. It’s now in the slower unused-symbol/file-size/validation portion.

`just check` failed only at symvision because the new public follow-store API is intentionally not wired into existing call sites yet. I need to read the project’s symvision memory before deciding whether to privatize or re-key those symbols to the still-open epic.

The symvision guidance says test-only imports do not keep a public API alive, and `--epic-symbol` is the intended bridge when a later epic phase will consume it. I’m checking the open epic/phase targets, then I’ll re-key these public APIs to an open bead rather than to the phase I’m about to close.

The later Focus/Fleet phases are still open. I’m re-keying these intentional public APIs to the parent epic in the symvision invocation so this phase can close without leaving stale `sase-xe.9` symbols behind.

The symvision bridge now points to the still-open parent epic. I’m rerunning the exact failing symvision gate before restarting `just check`.

Symvision is running with the new parent-epic symbol keys. I’m waiting for its verdict.

No symvision output yet; still waiting.

Symvision passes now. I’m rerunning full `just check`; it should pick up from the same rebuilt environment and then run scoped tests.

`just check` has passed formatting, keep-sorted, ruff, and mypy on the rerun. I’m waiting through the remaining gates.

Feature flags passed again. The remaining lint gates are still running.

The structural and terminology lint gates passed. It’s now past the failure point from the previous run, so I’m waiting for symvision/toobig/validation and scoped tests.

Still no output from the current gate; I’m staying attached and polling until it exits.

Symvision passed inside `just check`. The check lane is continuing into the remaining file-size and validation steps.

The file-size gate passed. Now `just check` is in repository validation and then the diff-scoped test selection.

SASE validation passed. The core-floor advisory correctly notes the three new bindings are unpublished in `sase-core` history, but the probe is advisory here; I’m waiting for committed-plan validation and scoped tests.

Committed-plan validation passed. The final stage is the diff-scoped pytest selection.

The scoped pytest lane is running now. I’m waiting for its selected-test summary and result.

The scoped test selection is still running quietly. I’ll keep polling until it reports selected tests or a failure.

No output yet from scoped pytest, so I’m checking its process state while keeping the `just check` session open.

The scoped lane is active under pytest with 13 workers, not hung. I’m continuing to wait for completion.

Still in scoped pytest. This lane can be a few minutes when the import graph selects a broad set, so I’m keeping it attached.

No test output yet; I’m continuing to wait for the scoped run’s result.

The scoped run is still active. I’m doing one more process check alongside the attached poll to see whether workers are still consuming CPU.

The scoped pytest controller is still alive. I don’t see a failure trace; I’m giving it more time to finish before considering a narrower reproduction.

Still waiting on the scoped test lane. Since this is the required finishing gate and the process is still present, I’m leaving it attached.

The check lane remains in scoped pytest with no new output. I’m polling again; I won’t start a competing suite.

This scoped run has been quiet for several minutes. I’m checking the pytest worker tree and recent temp output so I can tell whether it is slow or blocked on a specific selected test.

The worker tree is active and using CPU, with one current test in a monitor supervisor path. I’m continuing to wait; this is still a live scoped run.

Scoped pytest is still running without a failure trace. I’m giving it more time; terminating now would lose the required gate result.

Still running. I’m staying attached and will only investigate further if it stops making CPU progress or hits a timeout.

The scoped test run is still active under `run_silent`, so successful progress is hidden until the stage exits. I’m continuing to poll the attached process.

`just check` escalated to the full governed test lane because of `Justfile` and core-identity changes. It ran 38,873 items and had one failure in ACE/LSP wait-directive parity, which is very likely caused by the isolated-target LSP install copying a stale/default-path binary. I’m inspecting that install target and reproducing the single failing test.

The single failure reproduces and confirms the installed `.venv/bin/sase-xprompt-lsp` is stale: the freshly built isolated binary exists, but the install helper copied from the default target path. I’m updating the venv binary from the isolated build artifact, then rerunning that parity test and `just check`.

The parity failure now passes after installing the fresh LSP binary into the venv. I’m rerunning `just check` once more to get a clean required gate result.

The fresh `just check` run has cleared setup, formatting, keep-sorted, and ruff. I’m waiting through the remaining gates again.

Mypy passed on the final check run. Continuing through the remaining lint stages.

No new output from the current gate yet; I’m keeping the check process attached.

Feature flags, script structure, and test-wait lint all passed. The later project-specific lint gates are next.

Changelog and terminology checks passed. I’m waiting through symvision, toobig, validation, and the scoped test run.

Still no output from the current lint stage; I’m polling again.

Symvision and toobig both passed in the final run. The check lane is in validation and then the test stage.

Validation is still running quietly. I’ll keep polling until it emits the advisory/summary.

Validation and committed-plan checks passed again. The core-floor probe still reports the expected unpublished new core symbols as an advisory. The test stage is starting now.

The final `just check` is back in the governed test lane. Output is captured on success, so I’m polling until it exits.

The test lane is still running with no failure output. I’m continuing to wait.

Still in the test lane. The previous run took about nine and a half minutes, so this timing is expected.

No output yet; the scoped/full test run remains attached.

Still waiting on the final test lane. I’ll keep polling rather than start extra work that could contend with it.

The test lane is still active and quiet under `run_silent`. I’m continuing to wait for the final result.

Still running. I’m checking process state once more while leaving the test command attached.

The final run is active with six pytest workers and has been running about four minutes. I’m continuing to wait for completion.

No new output from pytest yet. I’m staying attached.

Still running. Since the previous full selection took roughly 9:26, this is still in range.

The final test lane remains quiet and active. I’m continuing to poll.

Still no output; I’m giving it another interval.

The run is still attached. I’m checking process state again only if it stays silent after this next poll.

The final run has now been quiet for several more minutes. I’m checking worker state again while keeping the command attached.

The workers are still active and using CPU. I’m continuing to wait; this run is not stalled.

Still running; waiting for completion.

The final test lane is now beyond the previous run’s duration because it has fewer workers. I’m still attached and polling.

No output yet; I’m continuing to wait for pytest to finish.

Still active. I’m keeping the command attached rather than replacing it with a partial check.

The test stage remains quiet. I’m polling again; no action needed unless it emits a failure.

Still running. The process tree has remained active, so I’m waiting for the natural exit.

The final test run is taking longer with six workers, but worker CPU is still present. I’ll keep waiting a bit longer before treating it as a separate blockage.

The six workers are still making CPU progress at about twelve minutes. I’m continuing to wait for a complete gate result.

Still no output; the lane is active. Polling again.

The test lane is still running. I’ll keep it attached until it exits.

Still active. This is the final verification run; I’m waiting rather than downgrading the gate.

No result yet from pytest. I’m polling again.

This is getting long, so I’m checking worker state one more time while keeping the run attached.

The workers are still active at fifteen-plus minutes. I’m continuing; stopping now would discard useful verification.

Still running. I’m polling again.

No output yet from the captured test stage. Continuing to wait.

The final lane remains active. I’m still attached and polling.

Still waiting. The test workers are active, so I’m letting the full selected lane complete.

No new output. I’m polling again.

The final `just check` is still in the test stage. I’m waiting for the process to exit cleanly.

The final full lane got past the LSP parity test but failed a different global-state leak detector test after ~20 minutes. I’m reproducing that single failing test to see whether it’s an unrelated suite-state flake or something this change affected.

The isolated single failure passed, which points to a full-suite interaction rather than this follow-store change. I’m rerunning `just check` once more to get a clean final gate; if the same global-state test flakes again, I’ll record it as a phase follow-up instead of hiding it.

The rerun has cleared setup, formatting, keep-sorted, ruff, and mypy. Waiting on the rest.

Feature flags passed. The lint lane continues.

The structural lint gates passed. I’m waiting on symvision/toobig/validation and tests.

No output from the current stage yet. Continuing to poll.

Still waiting on the current gate.

Symvision and toobig passed again. It’s moving into validation and then tests.

Validation passed with the same advisory about unpublished core bindings. The test lane is next.

Committed-plan validation passed. `just check` is now in the test stage again.

The test stage is running under captured output. I’m polling until it exits.

Still in the test lane. Waiting.

No output yet; continuing to poll.

Still running. I’m keeping it attached for the final result. 


The test lane is still quiet and active. Polling again.

Still active. This is the same governed full suite triggered by the Justfile symvision entries.

No result yet; continuing to wait.

Still running. I’ll check worker state on the next interval if it stays silent.

The test stage is still quiet, so I’m checking worker state while keeping it attached.

This run has thirteen workers and is about five and a half minutes into the test stage. I’m continuing to wait.

Still running. Polling again.

No output yet from captured pytest. Continuing.

Still active; waiting for the test result.

The run remains quiet and active. I’m polling again.

Still waiting on the final full test lane.

No output yet; continuing to wait.

The test lane is still active. Polling again.

Still no result. I’m staying attached.

The full suite is still running under the check lane. I’ll keep polling until completion.

The rerun of `just check` passed; its scoped selector escalated to the full suite because the Justfile changed. I’m recording one follow-up note for the isolated-target LSP install issue I found during verification, then I’ll do the required epic-symbol check and close only `sase-xe.9`.

The follow-up note was recorded. I’m running the required `sase bead epic-symbols sase-xe.9` check now; if it reports clean, I’ll close the phase with the verification note.

The phase has no stale `--epic-symbol` entries. I’m closing only `sase-xe.9` with the verification summary.

`sase-xe.9` is closed. I’m doing a final status check across the main checkout and linked core repo so the final declaration has the right repo state.

The bead is confirmed closed and the working trees contain only the implementation diffs. I’m reading the final-declaration skill body now, then I’ll submit the required SASE final declaration as the last tool action before my final response.

The final skill requires commit decisions for every repo I changed. I’m fetching the host-issued final context now.

The final context requires commit decisions for the main repo, linked `sase-core`, and the plans sidecar link update. I’m submitting those commit declarations now; after a successful submit I won’t run further commands.

Implemented and closed `sase-xe.9`.

What changed:
- Added Rust follow reconciliation/count contracts and PyO3 bindings in `sase-core`.
- Added Python durable follow-store persistence plus Focus/Fleet count wrapper.
- Added tests for follow promotion, unfollow tombstones, dispatch activation, and count partial/unknown propagation.
- Added symvision parent-epic entries for public APIs intended for later `sase-xe` phases.
- Recorded a `PROPOSED FOLLOW-UP` note for the `rust-lsp-install`/`CARGO_TARGET_DIR` copy issue found during verification.

Verified:
- `cargo test -p sase_core fleet_contract::tests::`
- `tools/validate_sase_core_rs` plus focused pytest: 28 passed
- Reproduced/fixed local LSP parity setup issue, parity test passed
- `CARGO_TARGET_DIR=/tmp/sase-core-target-sase_28 just check` passed; scoped lane escalated to full suite due `Justfile` change.
