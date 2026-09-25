# Chat History - ace-run (sase-zp.2)

- **TIMESTAMP:** 2026-09-11 17:29:33 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-zp.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-zp, bead=sase-zp.2)
%model:@medium
%auto
%w:sase-zp.1
%w(bead=sase-zp.1)
Can you complete the work for bead sase-zp.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-zp.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-zp.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-zp.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I’ll use the SASE bead/memory flow here: first I’m reading the relevant skill instructions, then I’ll inspect the bead and its design file, implement the phase, verify, clear epic symbols, and close only `sase-zp.2`.

I’m loading the bead lifecycle reference now so the close/update rules are fresh before I touch the bead record. After that I’ll pull the phase description and follow its design pointer.

The close rules confirm the important bit from your prompt: phase workers use notes for follow-ups and only close their own phase. I’m reading the bead now and checking its current epic-symbol obligations before changing code.

The phase is `bead_capacity`: add `-c/--capacity`, move clan selection to `-C/--cl-name`, and carry capacity through epic rendering, resume, and launch paths. I’m checking whether the plan file lives in a separate managed repo before reading it, so I use the right audited path.

That plan path is its own git checkout, so I’m switching to the SASE repo-opening skill before reading the design file. Small ceremony, but it keeps the sidecar access traceable.

I’ve got the repo-opening rules loaded; next I’m resolving the plans repo through `sase repo open` and then I’ll read only the referenced design file.

`plans` is registered in the repo inventory but not addressable by that short name through `repo open`, so I’m extracting its inventory row to get the exact identifier/remote. Then I’ll either open by the accepted reference or use the already resolved audited path from the bead command if the tool confirms it has no separate open alias.

I have an audited checkout for the plans repository now. I’m reading the design file from that printed checkout path and then I’ll map the requested capacity plumbing onto the local Python CLI/workflow code.

The phase’s scope is squarely in the Python bead work launcher, with Rust capacity parsing already owned by the prior phase. I’m going to search the work/launch code and tests for the existing clan-name, queue rendering, and launch argv paths before editing.

The search shows the Rust/Python queue contract already says `capacity`; this phase is mostly carrying that value through bead work. I’m narrowing into the actual entry points now instead of swimming in the whole repo.

The work parser currently uses `-c` for `--cl-name`, and the dispatch path only parses `--wait` before side effects. I’m reading the launch/render modules now; this is where the capacity value has to stay distinct from “waits” and zero must survive.

I see three prompt renders in `launch_epic_bead_work`: full preview, dry-run subset, and final selected launch. Capacity needs to be passed through each render, then into the detached/monitor argv builder for approved-plan handoffs.

The shared formatter already provides `format_queue_directive(capacity=...)` and `validate_queue_capacity`, which is handy. I’ll use that rather than duplicating bounds or syntax in the CLI layer.

One small snag: `make_args` in tests doesn’t include the new field yet, so I’ll update the test helper along with parser/dispatch. That keeps unit tests using the same shape as argparse without hiding missing defaults.

The plan-file error helper currently reconstructs only `--yes`, `--no-push`, and `--parent`; capacity has to be included there or failures will lose the user’s threshold. I’m checking the approval launch helper too, since it builds recovery text from the same argv function.

I’m going to make the code edits now: parser aliases, capacity validation, propagation through plan-file/bead-ID launch paths, prompt queue-line rendering, argv/recovery builders, and focused tests. After that I’ll regenerate the completion snapshot with the repo’s `just` target.

I’m editing the narrow path now. The core idea is a single optional `capacity` integer that gets validated once at the CLI/API edge and then passed unchanged into every render or recovery command.

I spotted a formatting slip in the task-launch call while reviewing the patch. Fixing that before moving on; no drama, just Python being very literal about whitespace.

Next I’m adding `capacity` to the plan-file result envelope only when it’s explicit, so JSON callers can see `0` without turning omitted capacity into noise.

I’m extending the plan-file resume-command helper now. This is the bit that keeps `--capacity 0` from evaporating in failure recovery text.

I’m threading that argument through plan-file creation and resume. This is mostly mechanical, but the important branch is the linked-plan resume path because it is where repeated `sase bead work plan.md` invocations continue an existing epic.

I’m doing a quick pass over those resume helper calls before patching the resume module; a missing call site here would be exactly the kind of tiny leak that makes a retry behave differently than the original command.

I found one secondary helper that also builds plan-file resume text for archive collisions. I’m giving it the same capacity parameter so all plan-file failure hints stay consistent.

Now I’m patching the linked-epic resume implementation. This handles archived plans with an existing `bead_id`, which is a common retry path for approved epics.

I’m moving into `launch_epic_bead_work` now: capacity will ride through full preview, dry-run subset rendering, final selected rendering, and the store-contention resume command.

For rendering, I’m adding a tiny queue-line helper around the Rust formatter. It inserts `%queue(capacity=N)` on every selected segment and leaves the old prompt byte-for-byte alone when capacity is omitted.

I’m updating the host-owned launch argv next. This is the path used by monitors, leased fallback procs, and completion failure “Resume with” notes.

The argv call sites are patched; I’m adding the two helpers behind them now: one validates via the shared queue contract, and one records the logical argv next to planner artifacts for durable orphan recovery.

I’m checking the patched launch module for any missed internal calls or signature mismatches before moving to the handoff file.

I’m updating the handoff’s pending JSON, but keeping the public completion notification payload unchanged. Only the private deferred record gets an optional recovery argv, which is the part that may reconstruct a launch later.

I’m adding optional capacity to the plan-approval epic launch entry points, even though the gate UI/schema phase will wire callers later. This makes the lower launch boundary ready without changing approval behavior yet.

The implementation path is in place. I’m scanning for any caller that still invokes a changed private signature or still assumes `-c` means `--cl-name`.

The system `python` is older than the project syntax, so that compile check was a tool mismatch rather than a source error. I’m rerunning with the repo venv and fixing my `rg` invocation.

I’ve got the main implementation trail from the handoff. I’m going to do a quieter verification pass now: read the CLI rule memory that applies to the new option, check the patched modules compile, then fill in the regression tests around capacity propagation.

The CLI memory confirms the new option needs a short alias and clean help, which matches the current `-c/--capacity` and `-C/--cl-name` shape. This checkout doesn’t have `.venv/bin/python`, so I’m checking the local tooling entry points before running compile/tests through the repo’s expected path.

Tooling is via `uv`/`just` here, so I’ll use those instead of assuming a virtualenv. Next I’m reading the existing bead-work tests and the directive type definitions so the new tests land in the same idiom.

The existing tests are neatly split: parser/multi-target behavior, bead validation, rendering, and launch plumbing each have their own home. I’m doing a syntax check through `uv` now, then I’ll patch the focused cases rather than making one giant catch-all test.

Syntax is clean now that `uv` created the local environment. I’m skimming the patched control flow next, mostly to catch boring things tests sometimes miss, like a retry path losing the capacity value or a JSON field being emitted inconsistently.

The first pass looks coherent: capacity is validated before side effects, plan-file and epic bead launches both receive it, and task/flag targets reject it. I spotted one small design nuance while reading: the durable handoff now records the exact resume argv only when monitor launch writes it, which is how unknown-outcome recovery keeps `0` distinct from omission.

I’m about to make the test edits. They’ll cover three layers: public parser/validation, rendered `%queue(capacity=...)` placement, and resume/recovery argv propagation through epic launch handoffs.

One tiny formatting wrinkle showed up in a continued argument list, so I’ll clean that while I’m in the tests. It’s the kind of thing `ruff format` would fix anyway, but better to leave the patch crisp.

I’m checking how queue directive conflicts surface before I assert that behavior. The renderer should compose with a land xprompt’s weight-only queue line, but a second authored capacity has to be rejected by the shared parser rather than silently winning.

The shared parser’s existing tests confirm the exact failure wording for duplicate capacity. I’ll reuse that boundary in the renderer tests: generated capacity plus a weight-only xprompt is valid, generated capacity plus another capacity is not.

I’m applying the test patch now: helper argument threading first, then the behavioral assertions in the existing test modules. After that I’ll run just the touched tests to shake out any bad assumptions.

The patch was too chunky for the patch tool because it touched the same file twice in one batch. I’m splitting it into smaller, cleaner edits now.

Helper threading is in. Next I’m adding parser and early-validation coverage around the new alias behavior and the “validate before any launch-side effects” guarantee.

The parser tests now assert `-c` belongs to capacity and `-C` belongs to `--cl-name`, with invalid capacity stopping before the code-swap lock. I’m adding the task-target rejection and ordered multi-target stop behavior next.

The CLI validation side is covered, including the ordered-success-then-stop case the bead specifically called out. I’m moving down into the prompt renderer now, where the capacity directive needs to appear exactly once in every selected epic segment.

The render tests now exercise omitted/default, explicit zero, subset relaunches, and composition with the land prompt’s weight directive. I noticed that file didn’t previously need `pytest`, so I’m adding that import before moving to launch plumbing.

Now I’m threading the same expectation through confirmed and dry-run launches, so both “what would launch” and “what actually launches” include the same capacity directive.

The prompt-level paths are covered. I’m adding plan-file resume coverage now, especially the places where an error says “resume with …” and must not drop an explicit zero capacity.

Plan-file resume now preserves capacity both on a linked-epic resume and on generated retry commands. Next is the host-side argv and monitor/proc recovery surface.

The monitor test now checks both argv propagation and the little durable `epic_launch_argv.json` breadcrumb used by orphaned handoff recovery. I’m adding the notification/recovery hint assertions now.

Failure notifications keep capacity now. I’m also covering the deferred planner-completion path, because that’s where a monitor can disappear before the launch outcome is known.

The handoff tests now pin the exact resume argv, including explicit zero capacity. I’m finishing the host approval tests so direct approved-epic launch helpers pass the same value into monitor start and into error hints.

Approval helper coverage is in. I’m cleaning the small indentation wart in the resume exception path, then I’ll run formatting and targeted tests.

The implementation and test edits are in place. I’m going to let the project tooling reshape imports/line wraps before running tests, then regenerate the completion spec for the CLI alias change.

Whitespace is clean. I’m using targeted Ruff formatting on only the touched Python files so the diff stays local to this bead.

Ruff only reformatted two files, which is pleasantly contained. I’m regenerating the checked-in completion spec now so the `sase bead work` option table knows about `-c/--capacity` and the moved `-C/--cl-name`.

`just sync-completion-spec` had to rebuild the local Rust binding because the linked core checkout moved, so it’s taking the scenic route through `maturin`. I’m keeping an eye on it rather than interrupting it.

Still waiting on the Rust build lock. Nothing has failed; it’s just queued behind another build in the shared checkout.

The build is still blocked on the Cargo build directory lock. Since this step updates a generated checked-in artifact, I’m giving it room to finish instead of racing it with another command.

It’s now been a couple of minutes on the build lock. I’ll give it one more poll, then if it’s still parked I’ll inspect what’s holding the lock without killing anything.

The sync step is still parked, so I’m checking the active build processes now. This should tell me whether it’s truly progressing or just wedged behind a stale lock.

There are several SASE workspaces building the Rust extension at once, and our sync job has active `rustc` work now, not a stale wait. I’m letting it finish; the good news is this should warm the cache for the later checks.

Still building. I’m not starting the test suite until this completes, because piling more Rust-linked commands on top would just make the queue worse.

No new output yet; this is still the same build wait. I’ll keep polling until it exits so we don’t leave a live session behind.

The command is still alive and quiet. I’m going to inspect active `rustc` age one more time in parallel, then continue waiting; no destructive action.

The Rust build is genuinely active across several workspaces, so I’m using the wait time for a light diff inspection. That should catch any test type or import issue before the heavier verification pass.

Diff inspection found one test helper capture that is fine at runtime but a little too loose for the type checker. I’m tightening that now while the Rust build continues in the background.

One more renderer nuance from the design file is worth pinning directly: land-only relaunches. I’m adding that assertion beside the subset relaunch case.

Land-only relaunches are now asserted too. I’m back to waiting on the generated completion spec step, which is still tied up in the Rust build.

Still no output. I’m doing another process peek to confirm it’s not a dead session; after the Rust extension finishes, the rest of the Python-side checks should be much quicker.

Confirmed: an active `rustc` is burning CPU, so this is slow rather than stuck. The diff is still exactly in the capacity path plus tests.

Still running; no failure output. I’m staying with it.

Still in the long Rust link/compile stretch. Once it exits, I’ll run the targeted Python tests first so we get useful feedback before the full `just check`.

No change yet; this is unusually long but still within a Rust extension rebuild under load. I’m going to keep the session open and avoid changing course unless it actually exits with an error.

Still quiet. I’m checking one last process snapshot at the ten-minute mark; if the compiler is still active, I’ll keep waiting rather than interrupting a generated-artifact command halfway through.

The active compiler is now several minutes into linking at high CPU, so it’s still real work. I’ll continue polling and keep the rest of the verification queued behind it.

Still running. The command is silent because `just sync-completion-spec` is inside the build step; no actionable output yet.

No new output, still attached. I’m not going to leave this running in the background; I’ll wait it out and then proceed with the tests.

While it compiles, I’m checking one possible assumption in the tests: the canonical spelling emitted by `format_queue_directive`. If the helper uses the short `%q:0` form instead of `%queue(capacity=0)`, I’ll adjust the assertions before running them.

I just realized one of my quick searches touched the linked Rust core checkout directly. The SASE repo rule wants linked repos opened through `sase repo open`, so I’m auditing that access now before relying on any of that context.

This project doesn’t have `sase-core` registered under a short name, so I’m opening it by GitHub identity as the repo tool suggests.

The opened core source confirms the formatter emits `%queue(capacity=N)`, so the new renderer assertions match the shared contract. Back to the still-running completion sync.

Still no exit from the sync job. It is not wedged, just very slow under concurrent Rust builds; I’m continuing to poll rather than leaving the workspace mid-command.

Still waiting on the same build. I know this is dull; at least it is keeping all later checks on the correct local binary instead of a stale one.

No new output yet. I’m going to keep the polling cadence steady; once the build unlocks, the command should continue into completion-spec generation.

It’s past the usual fast path, so I’m checking process state again. The deciding question is whether the linker is still getting CPU or has gone dormant.

Our own high-CPU `rustc` finished, but the wrapper is still waiting behind other Rust builds sharing the same target directory. I’m giving it a bit more time; this looks like target-lock contention rather than a local failure.

The shared target lock is now the bottleneck, not our code. To avoid waiting indefinitely behind unrelated workspace builds, I’m going to interrupt only my `sync-completion-spec` process and rerun it with an isolated Cargo target directory.

The interrupt landed cleanly on our own `just` process. I’m rerunning the sync with an isolated Cargo target now so unrelated workspace builds cannot hold this one hostage.

The isolated rerun is compiling normally now, with actual progress lines instead of a silent lock wait. This should get us past the generated completion spec step.

The build is into the local `sase_core` crate now, so the dependency compile wave is mostly past. I’m continuing to wait for the final Python extension link and spec generation.

Still compiling the core crate. No errors so far.

Core compiled; it’s on `sase_gateway` now. Still healthy progress.

Still building. This should be near the Python binding crate next.

No new lines yet, but the isolated build is still active. I’ll keep polling.

It reached `sase_core_py`, the extension crate. That’s the final heavy compile step before install and completion spec regeneration.

Still linking/building the extension crate. No failures.

Still quiet in the final extension build. I’m staying attached until it returns.

No new output yet. This is the final long part of the isolated compile.

Still waiting. The session is alive; it just has nothing to report during the extension link.

Still on the extension build. I’m not going to start anything else until this releases the environment.

Still running, no errors. This is all build time now.

The Python extension built and installed successfully, then the recipe moved into the matching LSP build. That is still part of the repo’s setup contract for this command, so I’m letting it finish too.

The LSP build is through most dependencies now. This second leg should be shorter than the Python extension compile.

It’s compiling `sase_core` for the LSP target now. Same source, different binary, so another short-ish core compile is expected.

The LSP target reached its final crate. We’re close to the completion-spec generation step itself.

`sync-completion-spec` finished cleanly after the isolated rebuild. I’m checking what generated files changed, then I’ll run the targeted test set.

The completion snapshot changed as expected. I’m running targeted lint/syntax checks now, then the capacity-focused pytest slice.

Ruff found one easy nit: `setattr(args, "capacity", ...)` wants plain assignment. I’m fixing that and rerunning the targeted lint.

Targeted Ruff and syntax checks pass. I’m running the capacity-focused test files now; this should tell us whether the new behavior is correct before the full project check.

The new tests are failing for one common reason, not thirteen separate bugs: Python is importing a `sase_core_rs` extension that doesn’t expose `parse_queue_capacity`, even after the setup build. I’m checking which extension file is actually being imported and whether the binding name differs in this checkout.

The installed package is definitely new enough by path, but its Python package surface only re-exports `collect_queue_fields` and `format_queue_directive`. The Rust file has `parse_queue_capacity`; the wrapper package is the missing link, so I’m inspecting that package shim.

The shim just re-exports the compiled module, so the compiled `.so` itself lacks the symbol. I’m checking whether the linked core checkout used by the build differs from the opened external checkout, and whether the local wheel cache served an older artifact under a too-broad key.

The source checkout and the opened external checkout are the same commit, and both have the Rust binding. The installed module still lacks it, so I’m checking the installed package metadata and shared object timestamps to see whether a stale dist-info or wheel overwrite happened after the build.

The setup step downgraded the venv back to the published `sase-core-rs 0.34.0`, whose existing Rust API already has queue-field collection but not the newer parse helper. I’m going to adjust the Python adapter to validate capacity through the older shared Rust `collect_queue_fields` contract, so the code still stays on the Rust backend boundary and works with the current dependency window.

I found the compatible route: `validate_queue_capacity` can feed a single capacity occurrence into `collect_queue_fields`, which is already present in the published Rust package. I’m patching that adapter so all callers stay on the shared Rust validation contract without needing the newer parse-only binding.

The adapter patch is in. I’m formatting/checking that small change, then rerunning the same targeted test slice.

The older Rust collector understands capacity through the positional `%q:N` form, not the newer `capacity=` keyword. That’s still the same Rust contract, so I’m switching the adapter payload to the positional form.

The adapter now uses `%q:N` for validation. I’m checking the behavior directly before rerunning the suite.

The positional collector succeeds differently in the current published wheel: it reports the field under the legacy `runners` name. I’m making the adapter accept either `capacity` or `runners` from Rust so it bridges the dependency window cleanly.

I’m checking the formatter too, because the older Rust wheel may still render the legacy field name if it receives `capacity`. The adapter can normalize both directions if needed while preserving the public `%queue(capacity=N)` spelling required by the bead.

The current published Rust API still calls the field `runners`; the Python side already presents it as `capacity`. I’m going to normalize the adapter at that boundary: old Rust gets `runners`, Python callers get `capacity`, and generated prompts still use the public `%queue(capacity=...)` spelling.

The dependency range intentionally allows `sase-core-rs 0.34.0`, so changing only the lock/floor would be brittle. I’m adding a compatibility shim in `queue_directive.py` that retries old-core field names only when the old-core error is detected.

I’m patching the queue adapter in both directions now: call modern Rust with `capacity` first, retry legacy Rust with `runners` only on the old compatibility error, and normalize returned fields/messages back to `capacity`.

The compatibility normalization is in. I’m running the adapter’s own checks and a small direct probe before the larger retry.

The direct adapter probe now works against the currently installed old wheel and still emits the public `%queue(capacity=...)` spelling. I’m adding the queue adapter test file to the targeted suite so this compatibility layer is covered explicitly.

The remaining failures are old-wheel-only: the Rust typed-launch path itself is still emitting legacy `runners`. Since setup now has the missing dev dependencies installed, I’m rerunning `just install` with the isolated target so the local venv stays on the linked `sase-core-rs 0.34.13` instead of being downgraded again.

`just install` restored the local venv to `sase-core-rs 0.34.13` using the cached wheel. I’m rerunning the targeted tests now; this should separate actual patch issues from the stale-extension noise.

`uv run` is helpfully syncing from the lock before pytest and undoing the local core install. For this repo’s dev flow, the stable test runner after `just install` is `.venv/bin/python -m pytest`, so I’m switching to that for targeted tests and for the later `just` checks.

As expected, `uv run` put the venv back on `0.34.0`. I’m restoring the linked-core wheel one more time, then I’ll avoid `uv run` for pytest.

The venv is restored. I’m confirming the binding is present, then rerunning the targeted suite using `.venv/bin/python` directly.

The binding is present on `0.34.13`. Running the targeted tests now without `uv run` so it won’t resync the lockfile version underneath us.

Targeted tests are green: 130 passed. Before I run the required full verification, I’m reading the project’s lint/test memory because this repo makes that mandatory after tracked-file edits.

The memory confirms `just check` is the required agent gate. I’m running it inline with the isolated Cargo target, so the Rust bits should stay warm and we avoid the shared build lock that slowed us down earlier.

`just check` is through formatting, keep-sorted, and Ruff. It’s still running the broader lint gates and scoped tests.

`just check` made it to mypy and found a single local issue: two `payload` variables in the same function scope. I’m renaming the epic success one, then I’ll rerun the gate.

The mypy no-redef is fixed. Rerunning `just check` now; the Rust setup is warm, so this should pick up where the prior run exposed the type issue.

The rerun is through the same early lint gates. Waiting on mypy and the rest now.

Mypy is green now. The remaining `just check` gates are still running.

`just check` now passes formatting, Ruff, and mypy, then stops on an unrelated existing feature-flag lint: live flag bead `sase-z9` has no registry definition for `completion_managed_install_recipe`. Per your instruction, I’m recording that as a `PROPOSED FOLLOW-UP` note on this phase instead of creating or closing any other bead.

The follow-up note is recorded on `sase-zp.2`. I’m rerunning the targeted capacity suite after the small mypy rename, then I’ll do the required epic-symbol check before closing the phase.

The targeted suite is green again. I’m checking the bead’s epic-symbol list now; if it’s clear, I’ll close only `sase-zp.2` with a note that includes the targeted tests and the unrelated `just check` blocker.

The epic-symbol list is clear and the diff has no whitespace errors. I’m closing only `sase-zp.2` now with the verification note, including the unrelated `just check` feature-flag blocker so the land agent has the breadcrumb.

`sase-zp.2` is closed. I’m doing the final status/context pass now, then I’ll submit the required SASE final declaration as the last tool action before I answer.

The bead now shows closed with the verification note and the proposed follow-up note. I’m reading the SASE finalizer instructions one last time so the final declaration is shaped correctly, then the submit command will be my last tool action.

I’ve got the implementation and verification state from the prior run. I’m just loading the final-declaration skill now, then I’ll submit the required SASE final marker and give you the short wrap-up.

The finalizer skill expects a host manifest, and since this turn changed the primary repo, I’m going to declare that work for the host commit finalizer rather than trying to make a commit myself.

All dirty paths are from this turn, including the regenerated completion snapshot, so the final manifest will ask the host to commit the main repo changes as one `feat(bead)` stitch.

Done. `sase-zp.2` is closed.

I added `sase bead work -c/--capacity`, moved CL name short alias to `-C`, and carried capacity through epic plan rendering, resume, dry-run/JSON, launch, monitor, handoff, and retry paths. Capacity now renders as `%queue(capacity=N)` for selected phase/land segments, omits when unset, and preserves explicit `0`.

Verification: `sase bead epic-symbols sase-zp.2` was clear; targeted capacity tests passed (`130 passed`); `git diff --check` was clean. `just check` passed fmt, keep-sorted, ruff, and mypy, then stopped on an unrelated existing feature-flag lint issue for `sase-z9`; I recorded that as a `PROPOSED FOLLOW-UP` note on `sase-zp.2`. Final commit declaration was accepted.
