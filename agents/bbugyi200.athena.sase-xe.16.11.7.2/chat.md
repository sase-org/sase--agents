# Chat History - ace-run (sase-xe.16.11.7.2)

- **TIMESTAMP:** 2026-09-09 17:06:31 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-xe.16.11.7.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-xe.16.11.7, bead=sase-xe.16.11.7.2)
%model:@medium
%auto
Can you complete the work for bead sase-xe.16.11.7.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-xe.16.11.7.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-xe.16.11.7.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-xe.16.11.7.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I’ll inspect the bead and its referenced design, then make the scoped code change and verification. I’m using the SASE memory-read and final-declaration skills because this task involves bead operations and a SASE turn closeout.

I’m reading the bead-specific reference memory first, since the project treats bead queries and closes as audited workflow operations. After that I’ll inspect the phase description and design reference.

The bead rules are loaded. I’m checking the phase record now, including any artifact or plan references that point to the design file.

The bead has no direct artifact refs, so the design file is likely attached through the parent plan metadata. I’m waiting on the full bead/dependency output before following that link.

The phase is `attention-wire`: it needs a bounded fleet-wide pending-attention inventory contract, and it blocks a later ACE projection phase. I’m reading the parent design file now to see the intended API and phase boundaries.

The design says every phase must read the linked research and predecessor plan via `sase artifact read`; I’m loading the artifact workflow rules before consuming those references. Then I’ll narrow to the `attention-wire` implementation notes.

The design narrows this phase to Rust/gateway/federation/PyO3 attention inventory contracts, not ACE rendering yet. I’m now consuming the required research and predecessor artifacts through the audited artifact path before touching code.

The artifact reads are still running. Once they return, I’ll map the required contract to the current Rust and Python surfaces rather than assuming names from the design.

Two required research artifact reads reported a missing document root and pointed at the research sidecar. I’m opening that repository through `sase repo open` as instructed, then I’ll retry the audited reads.

The repository inventory is noisy but useful: `sase-core` appears as an external repo, and the research sidecar has a local candidate path. I’m waiting for the explicit research open to finish before retrying artifact reads.

The research sidecar is open at the audited path. I’m retrying the research reads and also recording an audited read of the current design plan.

The audited artifact reads are still executing. I’ll use their concrete acceptance points to decide how much belongs in this phase versus later ACE UI phases.

I have the acceptance points: owner-side pending inventory, stable request identity, federation fan-out, PyO3 validation, and zero-machine laziness. I’m opening `sase-core` through the SASE repo workflow because the shared contract belongs there.

`sase-core` is now opened for this workspace. I’m doing targeted source discovery around the existing attention route and bindings so the new inventory surface fits the current code rather than duplicating it.

The current code already has row-scoped attention resolution and a logical-key attention read. I’m reading those definitions and the federation route next; the new work should extend that surface with inventory, not break the existing bounded-key hydration path.

The existing core type has request-key and revision fields on each row already, but the read contract is still keyed by known logical agents. I’m reading the projection code and gateway handler to add a separate inventory path with pagination and coverage.

The gateway route currently proves the old behavior: empty keyed attention requests deliberately avoid the notification store. I’m checking the shared cursor and freshness types so the inventory response can expose continuation and unknown coverage cleanly.

The local gateway notification list already has sort and limit helpers, but the fleet attention route reads everything after resolving followed rows. I’m checking the read-service and route-test scaffolding before editing.

The new core surface will be mostly additive: request/page validation plus a paged projection over notification rows. I’m checking validation helper visibility and Python binding conventions before patching.

The likely shape is clear: keep `/attention` as row-scoped, add `/attention/inventory` for fleet discovery, and add validation bindings for the new request/response envelopes. I’m checking the Python facade and binding loader so downstream phases have names they can consume.

The Python facade has an explicit disabled-read fast path, so zero-machine laziness can be preserved by routing inventory through the same `_read` mechanism. I’m reading the existing attention tests to add small coverage without pulling ACE into this phase.

The binding crate has in-Rust PyO3 tests, so I can verify the new exported names without relying on the currently installed Python wheel. I’m going to patch the Rust contract, gateway route/worker op, and the thin Python facade now.

The core contract now has additive inventory request/response types and validation. I’m adding unit coverage for uncorrelated discovery, pagination, revision stability, and validation failures before wiring the route.

I’m continuing from the existing bead context and checking the partial core patch first, then I’ll wire the same contract through gateway, worker, bindings, and Python dispatch before closing only the assigned phase bead.

The core inventory types and their first unit tests are present; the remaining work is mostly export plumbing and callers. I’m checking the local export patterns now so the added API matches the existing wire contract style.

The core test patch did apply. I found one thing to tighten while exporting it: inventory validation should keep `has_more` and `next_cursor` consistent so downstream clients can rely on the continuation envelope.

I’m about to make the scoped edits in the core repo: public exports, gateway route, federation operation, PyO3 bindings, and the validation consistency tweak.

I’m editing the core repo now, keeping the existing row-scoped `/attention` behavior intact and adding a separate inventory path for discovery.

Core projection validation is tightened. Next I’m adding the public exports and wire re-exports so the gateway, worker, and Python binding all use the same Rust contract types.

The gateway route is next. I’m adding inventory as a separate authenticated read endpoint, with freshness metadata and no dependency on followed logical keys.

Now I’m adding the federation worker operation so fleet controllers can fan out the inventory request with the same deadline, cache, and per-host degradation behavior as existing fleet reads.

The worker operation is in place. I’m adding PyO3 binding functions next, following the existing dictionary-to-wire conversion path so Python callers get the same validation errors as Rust callers.

I’m keeping the binding surface explicit: one projection call and two validator calls for the inventory request/response envelopes.

The binding functions are defined; I’m registering them in the module initializer so Python can import them.

I’m reading the existing gateway and worker tests around attention so I can add the new coverage beside the closest existing cases instead of introducing a separate test style.

I’m adding gateway tests for three specific contracts: missing read scope, uncataloged pending entries appearing in inventory, and cursor paging that filters settled items.

I’m adding worker coverage now: empty-fleet laziness, a stable namespaced cache key, and then exercising inventory through the real deadline fan-out test.

The worker capability list now advertises inventory explicitly. I’m adding a direct PyO3 regression test for the new projection and validator functions so the exported Python shape is covered before any wheel is cut.

I’m patching the PyO3 tests now with a minimal owner-side question row. That exercises an uncataloged pending entry without depending on gateway filesystem state.

I’m adding one more direct request-validator assertion in that binding test, so both inventory envelopes have explicit coverage.

Core-side changes are mostly wired. I’m switching to the Python dispatch facade now, adding a public inventory fetch that does not short-circuit on empty logical-key input.

I’m adding `attention_inventory` to the Python facade in the same shape as other read operations, so disabled configs return the standard empty-hosts envelope.

The high-level attention client is next. I’m adding `fetch_remote_attention_inventory` as a fleet-wide discovery call, while leaving `fetch_remote_attention` as the row-scoped hydration path.

I’m updating Python tests to cover the disabled/no-host behavior for inventory and the public helper’s request construction.

The implementation patches are in. I’m formatting the Rust workspace now, then I’ll run focused tests and fix any compile or contract issues that shake out.

Formatting completed. I’m starting with the pure core inventory tests because they validate paging, pending-only filtering, stable request identity, and cursor/limit validation before the network layers get involved.

The first cargo test is building and currently waiting/compiling under Cargo’s package cache lock. I’ll let it finish before starting other Rust tests to avoid compounding the lock wait.

The pure core test is still running through compilation with no failure output yet.

Still no error output from the core test build; I’m continuing to wait for the active session rather than launching competing cargo jobs.

The pure core inventory tests passed. I’m moving to gateway route and federation-worker tests next, where most integration mistakes would show up.

The gateway test run is waiting on Cargo’s build-directory lock. No failures have appeared yet.

Gateway tests are still waiting/building under Cargo. I’m holding on that session until it returns.

The gateway test command is still active with no diagnostics yet.

Still blocked on the existing Cargo test session; I’m continuing to wait rather than interrupting a potentially near-complete compile.

The filtered gateway run compiled successfully but did not execute any tests, so I’m listing the gateway test names to confirm the exact filters before relying on it.

The gateway list surfaced a stale-build issue: the unit-test list did not include the new tests, while doctest compilation saw the gateway edits but linked a stale `sase_core` without the new module items. I’m checking the workspace dependency wiring before rerunning with a clean enough build target.

Cargo is clearly reusing stale target artifacts, so I’m going to clear only the affected Rust package build artifacts (`sase_core` and `sase_gateway`) and rerun the focused gateway tests against the current source.

The clean completed and removed a large shared target cache for those packages. I’m rerunning the focused gateway inventory tests now; this will take longer because it must rebuild dependencies.

The gateway test rebuild is underway from a clean target. I’ll keep polling until it either fails with concrete diagnostics or finishes.

`sase_core` rebuilt and the gateway crate is compiling now.

The gateway route inventory tests passed. I’m running the federation-worker inventory tests, including the real deadline fan-out case.

Cargo only accepts one test-name filter before harness args. I’m splitting that into valid focused runs.

The worker inventory test run is waiting briefly on the build lock again, likely from rustdoc/test cleanup.

The worker inventory cache/laziness tests passed. I’m running the deadline fan-out test now, which includes the new inventory operation after the existing summary checks.

The deadline fan-out test passed. I also changed the existing missing-scope test to cover the new endpoint, so I’m running that one explicitly.

The gateway auth and route tests passed. I’m running the new PyO3 inventory binding test next.

Same cargo filter limitation; I’m splitting the PyO3 binding checks.

The PyO3 binding test is waiting on Cargo’s build lock and should move into compilation shortly.

The PyO3 command is still active without diagnostics.

The PyO3 crate is compiling now.

Still waiting on the PyO3 test compile; no error output yet.

The PyO3 compile is still running. I’ll keep this session open until it completes so no background process is left hanging.

The direct PyO3 inventory binding test passed. I’m running the module-registration test too, because I added the new names to the exported module.

The core PyO3 tests passed. I’m running the Python dispatch tests now for the facade and high-level attention client changes in the main repo.

The Python dispatch tests passed. I’m running the existing row-scoped attention laziness test once more because preserving that empty-logical-key behavior is a key part of this phase.

The row-scoped empty-read laziness test passed. I made more Rust edits after the first formatting run, so I’m running `cargo fmt` once more before broader checks.

Formatting is clean. I’m reviewing the diff and checking for any accidental broad changes before running the repo’s required verification guidance.

The focused tests are passing after the clean rebuild. I’m checking gateway doctests once, because the earlier stale-artifact failure showed up in rustdoc rather than the unit harness.

Gateway doctests are waiting on the build lock again; I’ll wait for the result.

The doctest command is still active with no error output.

Still waiting on gateway doctests; no diagnostics yet.

Gateway doctests now pass against the rebuilt core. I’m rerunning the pure core inventory filter once more so the final verification set reflects the current target state after the clean.

The core inventory rerun is waiting briefly on Cargo locks.

The core rerun is still active with no failures reported.

One anomaly remains: the core inventory filter passed but did not include the new `fleet_attention` test names in its output. I’m listing core tests now to verify whether the new tests are being built or whether the harness filter is behaving unexpectedly.

The full core test list was too large to be useful in the log. I’m using the fully qualified test prefix now so the harness can only select the new fleet-attention inventory cases.

The fully qualified core test run is waiting on the build lock.

The fully qualified filter still selected zero tests, which means those new core tests are not in the compiled harness despite being in the source. I’m checking whether the test module has conditional boundaries or a name collision hiding that block before proceeding.

The source block is valid and carries `#[test]`; the zero selection is a harness-filter mismatch. I’m going to run one exact function name without the module prefix to force the selection.

The exact core inventory test is waiting on the build lock; the previous exact projection test confirmed the harness is seeing this module.

Still waiting on the exact core inventory test session.

The exact inventory test is still active with no diagnostics; I’ll keep the session open.

Cargo is still holding the exact inventory test session; no failures yet.

The exact core test is taking longer than expected because of Cargo locking, but it has not emitted any compiler or test failure output.

Still waiting on the same Cargo session; I’m keeping it open rather than abandoning it.

The core test command remains in the Cargo lock wait. If it continues much longer I’ll inspect active Cargo processes, but I won’t start another build while this one is pending.

The Cargo lock wait is now excessive, so I’m checking active Cargo/rustc processes to see what is holding the lock before deciding how to proceed.

The lock is held by another long-running workspace build outside this turn; my exact inventory test is queued behind it. I’ll wait for the queued command to finish rather than killing unrelated work.

The exact filter still selected zero, so I’m checking the harness list through `rg` directly. If those names are absent, I’ll force a private target rebuild for `sase_core` to remove shared-cache ambiguity.

The filtered harness-list command is also queued on the shared Cargo lock, which matches the active workspace build I saw.

Still waiting on the shared build lock for the harness-list command.

The command remains queued. I’m not going to launch another Cargo build until this session clears.

Still waiting on the same shared Cargo lock. The earlier focused gateway/PyO3/Python tests already passed; this extra step is to remove uncertainty around the pure-core inventory test filter.

The new core test names are absent from the harness list, which points to stale dep-info rather than bad source. I’m touching the affected Rust source to force Cargo to rebuild the test harness from the current file contents, then rerunning one exact inventory test.

The file timestamp is updated; I’m rerunning the exact test name now.

The touch forced a `sase_core` rebuild. I’m waiting for the exact inventory test result.

The rebuilt core inventory test is still compiling/running with no failure output.

The exact core inventory test now runs and passes after the forced rebuild. I’m running the `inventory_` filter to cover all four new pure-core inventory tests together.

The all-inventory core filter is queued on the build lock again; it should be a quick run once the lock clears.

Still waiting on the shared Cargo lock for the grouped core inventory test.

The grouped core inventory test is still queued; I’m continuing to wait on the active session.

Still no output from the grouped core inventory run beyond the Cargo lock wait.

The grouped test is still blocked behind the shared build directory lock. The single exact test already passed; I’m waiting because this grouped run is still an active session.

The grouped core inventory tests now include and pass all new fleet-attention inventory cases. I’m reading the repo’s required verification note before finishing changes to tracked files.

The verification note requires `just check` for main-repo changes. I’m running it inline now; if it turns into a prolonged wait, I’ll keep reporting the concrete state.

`just check` detected and installed the current `sase_core_rs` wheel, then started rebuilding the linked core/LSP pieces. It is still running.

`just check` is compiling the linked `sase_core` checkout as part of environment validation.

The required check is still compiling; no failure output yet.

The linked LSP rebuild finished. `just check` has moved on to setup and plugin validation.

`just check` has passed formatting, keep-sorted, and ruff; it is still working through the remaining lint/test gates.

The check is still running with no new failure output.

`just check` passed mypy and continues through the remaining gates.

Feature-flag lint passed; the check is still active.

More lint gates passed: pyscripts, test-waits, and changelog.

Patch/stitch terminology lint passed; `just check` is still running.

`just check` failed at symvision because of a pre-existing stale `--epic-symbol` for closed bead `sase-yy.4`, not because of this attention inventory work. Per your instruction not to create beads, I’m recording that as a proposed follow-up on this phase bead and continuing with this bead’s required symbol audit.

The follow-up note was recorded on the assigned phase bead. I’m running the required `epic-symbols` check for `sase-xe.16.11.7.2` now.

The required phase symbol audit is clean: no `--epic-symbol` entries are keyed to `sase-xe.16.11.7.2`. I’m checking working-tree state in both repos before closing the bead.

The main repo and external `sase-core` checkout contain only the expected edits; the linked core checkout used by `just check` is clean. I’m closing the assigned phase bead with the verification summary now.

The phase bead is closed. I’m doing the final status check now, then I’ll submit the SASE final declaration as the last action before my response.

The bead is confirmed closed. I’m invoking the SASE finalizer flow now; after a successful final declaration I won’t make any more filesystem or bead mutations.

The finalizer requires commits for two repositories: main and the external `sase-core` checkout. I’m submitting those commit intents now with scoped messages; this is the last tool action before my final response.

Completed and closed `sase-xe.16.11.7.2`.

Implemented:
- Core pending-attention inventory wire contract, projection, paging, validation, and PyO3 bindings.
- Gateway `POST /api/fleet/v1/attention/inventory`.
- Federation worker `attention_inventory` fan-out operation.
- Python dispatch facade/helper for fleet-wide attention inventory reads.

Verified with focused Rust/Python tests, plus the required `sase bead epic-symbols sase-xe.16.11.7.2` audit, which reported no entries for this bead.

`just check` was run but failed on an unrelated stale symvision `--epic-symbol` for closed bead `sase-yy.4`; I recorded that as a `PROPOSED FOLLOW-UP` note on this bead as instructed. Finalizer declaration was accepted for the main repo and external `sase-core` changes.

I’m going to use the SASE repo workflow for the external checkout and the SASE final declaration path, then inspect the paused merge state directly in the target repo.

The repo skill requires an audited open before I touch the external checkout. I’ll use the printed path for all subsequent commands and keep every command scoped with an explicit working directory.

Next I’m checking the live unmerged state and the target repo’s local instructions/verification entry points before looking at any conflicted file content.

There is one unmerged file in the Python binding crate, with several already-merged Rust changes staged/modified around fleet attention and gateway wire/routes. I’m reading the repo instructions and command definitions now so verification matches this repo, not the parent workspace.

The repo’s required gate is explicit: `just check` from the `sase-core` root. I’m now using git’s unmerged stages to understand both sides of the binding conflict rather than relying on the working tree markers alone.

The conflict is a same-list/same-test collision: one side added fleet federation/catalog bindings, the other added pending attention inventory bindings and tests. The correct resolution should keep both sets and check for any duplicate or missing registration.

I’m editing the binding file to preserve both sides: import all required wire types, register both federation/catalog and attention-inventory functions, and keep the added attention-inventory envelope test.

The conflict markers are removed in the working file. I’m checking the resolved regions and the full diff now before staging, then I’ll run the repo’s required gate after the index reflects the resolution.

The resolved binding file now has no conflict markers and keeps both APIs. I’m staging it, then I’ll review the complete staged patch, including automatically merged files, before running the required repo gate.

`just check` is backed by this repo’s `scripts/check.sh all`, which runs `cargo fmt --all -- --check`, workspace clippy, and workspace tests from the repo root with Python 3.12+ selection. I’m reviewing the staged patch now.

The staged patch touches six files and `git diff --cached --check` is clean. I’m reading the staged diffs by subsystem to catch list/enum/API integration issues, especially around the new gateway route and Python exports.

Core exports and wire re-exports look like additive inventory types/functions with bounded pagination checks. I’m continuing through the gateway worker/routes and Python binding diff because those are where duplicate enum variants or missing registration would show up.

The staged review shows the conflict resolution is additive: one new `/attention/inventory` read path through core, gateway, federation worker, and Python bindings, with the existing catalog/federation bindings retained. I’m running the mandatory `just check` from the `sase-core` repo root now.

The required gate is still running after the initial compile phase. I’m waiting on the same session rather than starting any parallel repo mutations.

`just check` failed in clippy before tests, but not in the conflict hunk: `py_bead_remove_link` already has 8 parameters and now trips `clippy::too_many_arguments` under `-D warnings`. I’m checking local patterns before deciding whether the smallest verification repair is an explicit lint allowance on that PyO3 binding.

The smallest local repair is consistent with adjacent bindings: `bead_add_link` already uses an explicit `#[allow(clippy::too_many_arguments)]` for the PyO3 signature shape. I’m adding the same allowance to `bead_remove_link` so the mandated all-changes gate can run cleanly.

I’m staging that clippy allowance and rechecking the staged patch for markers/whitespace before rerunning `just check`.

There are no conflict markers anywhere in the target checkout. I’m doing the staged whitespace check and a focused staged diff review of the new lint allowance before rerunning the full gate.

The staged patch is clean after the lint allowance. I’m rerunning the full required `just check`; if it passes, I’ll continue the paused VCS operation.

The rerun has completed format/clippy and is in the workspace test compile/run phase. I’m continuing to wait on the same gate session.

The full gate is still compiling the workspace tests. No new action is needed until that session exits.

The gate is still running under `cargo test --workspace`; I’m holding off on resume until it gives a clear result.

`just check` is still active with no new output in the last poll. I’m continuing to wait on the same process so the verification result is unambiguous.

The workspace test phase is taking a while but is still running. I’m waiting rather than interrupting it because this repo’s instructions make the full gate mandatory.

The second `just check` got through clippy and most workspace tests, then failed when the PyO3 test binary could not load `libpython3.14.so.1.0`. The repo script permits setting `PYO3_PYTHON`, so I’m checking for a Python 3.12/3.13 interpreter with a usable shared library and will rerun the same required gate with that explicit interpreter.

All Python 3.12-3.14 executables are uv-managed under `~/.local`, so the shared library directory is not on the dynamic loader path by default. I’m rerunning the required `just check` with `PYO3_PYTHON=python3.12` and that interpreter’s `lib` directory on `LD_LIBRARY_PATH`.

The third `just check` is running with the explicit Python 3.12 runtime configuration and has passed the initial clippy/build segment. I’m waiting for the workspace tests to finish.

The explicit-Python gate has reached doc tests with all reported unit/integration suites passing so far. I’m waiting for the final process exit.

The required gate passed with `PYO3_PYTHON=/home/bryan/.local/bin/python3.12` and the matching uv lib directory on `LD_LIBRARY_PATH`. I’m checking the paused git operation state, then I’ll continue it and handle any further conflicts if they appear.

Git reports an interactive rebase with all conflicts fixed and no commands remaining. I’m continuing that rebase now using a non-interactive editor setting.

The rebase continued successfully and created the rebased commit. I’m now running the required `sase stitch create --resume` from the target checkout.

`stitch create --resume` is still running with no output yet. I’m waiting on that process before inspecting final repository state.

The resume command remains active and quiet. I’m continuing to wait rather than issuing overlapping VCS operations.

`stitch create --resume` is still running after another poll with no output. I’ll keep waiting on the same process unless it reports a conflict or failure.

The resume process has been silent for about two minutes. I’m going to inspect the process tree only, without touching git state, to see whether it is waiting on a child process.

The resume process is still alive as a `sase stitch create --resume` Python process; the process tree suggests it has launched SASE-side work rather than blocking in git. I’m continuing to wait for the command’s own result.

`stitch create --resume` remains active and quiet. I’m keeping the turn open until it exits, as requested by the recovery instruction.

The resume command reports that the primary commit succeeded, with an agent-hood publication quarantine warning. It has not exited yet, so I’m waiting for the final status.

`stitch create --resume` exited successfully after the primary commit warning. I’m checking the final target repo state and latest commit before preparing the SASE final declaration.

The target repo is clean on `master`, and the latest commit is `86a1ab6 feat(fleet): add pending attention inventory contract`. I’m now entering the mandatory SASE final declaration flow.

Resolved the paused `gh:sase-org/sase-core` rebase conflict and resumed the stitch.

Conflict repair:
- Resolved `crates/sase_core_py/src/lib.rs` by keeping both sides: existing fleet catalog/federation bindings plus the new pending attention inventory bindings/tests.
- Added the matching `#[allow(clippy::too_many_arguments)]` on `py_bead_remove_link` after the required gate exposed the same PyO3 signature lint pattern already used nearby.

Verification:
- `git diff --cached --check`: passed.
- Conflict marker scan: no markers found.
- Required repo gate: `just check` passed with explicit Python runtime env:
  `PYO3_PYTHON=/home/bryan/.local/bin/python3.12`
  `LD_LIBRARY_PATH=/home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib`

Continuation:
- `git rebase --continue`: succeeded.
- `sase stitch create --resume`: succeeded.
- Latest target commit: `86a1ab6 feat(fleet): add pending attention inventory contract`.
- Target repo is clean. The resume command warned that agent-hood publication has quarantined requests, but the primary commit succeeded.
