# Chat History - ace-run (sase-uv.2)

- **TIMESTAMP:** 2026-08-27 14:04:04 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-uv.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-uv, bead=sase-uv.2)
%model:@medium
%auto
Can you complete the work for bead sase-uv.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-uv.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-uv.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-uv.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I’ll use the SASE memory/finalizer skills because this task touches bead lifecycle and must end with a SASE final declaration. I’m going to read the required skill instructions, then inspect the bead and its design context before editing.

The bead workflow has project-specific lifecycle rules, so I’m reading the bead reference memory through the audited command before I run bead commands.

I’m checking the bead record and current tree state now. That should identify the design file, existing assignments, and whether there is unrelated work already in the checkout.

The git status was clean at the start of the work. The full file listing was noisy, but the key next step is the bead record, which is still returning output.

The phase is about removing provider/icon discovery work from ACE keystrokes. I’m reading the epic plan next so the implementation stays aligned with the intended phase boundaries.

The plan confirms this phase is narrowly about the acute keystroke path: table-driven fixed pane descriptors, memoized fixed descriptors, and stale-while-revalidate artifact subtab discovery. I’m continuing through the phase-specific sections before touching code.

The plan explicitly says the companion research report is load-bearing for this phase. Because that report lives in a linked repository, I’m switching through the SASE repo workflow before reading it.

The report is linked as a SASE artifact reference, so I’m reading the artifact workflow memory before consuming it. That keeps the read audited instead of treating it like an ordinary file.

I’ve got the bead and artifact lifecycle constraints loaded. I’m reading the linked research report now, then I’ll inspect the concrete TUI code paths named by the phase.

The artifact read is still running; I’m waiting on that before implementation so the telemetry details don’t get skipped.

The artifact registry couldn’t resolve the research ref, but it reported a concrete candidate path. Since the source is a linked repo, I’m opening that repo through `sase repo open` and will read the report from the audited checkout path it returns.

The linked repo open is taking a few seconds, likely preparing the checkout. I’m letting it finish rather than reading the path directly.

The research checkout is open at the path provided by SASE. I’m reading the report sections that support the keypath fix, then I’ll move into code.

This phase directly changes ACE responsiveness behavior, so I’m reading the TUI performance memory before edits. The relevant constraints are event-loop work, render-path filesystem access, and keystroke subprocess safety.

I’ve loaded the phase plan, the research report, and the TUI performance rules. Next I’m inspecting the named code paths and the existing tests so the change follows the current architecture rather than adding a parallel mechanism.

The existing LinkSubject mixin already has a background index refresh; the expensive part still happens while deciding availability and resolving presentation for fixed panes. I’m checking the initialization and tests around that so any new cache has a clear invalidation point.

The current tests already include a regression note for provider-token lookup in link index construction, so I’m reading those alongside artifact discovery tests. The goal is to extend the guard to keystroke and fixed-pane resolution paths.

The action-availability code currently delegates `$` availability to `link_edges_for_selection()`, which still resolves a full subject. I’m going to inspect the link index builder next because fixed-pane icon resolution is used both for selected subjects and neighbor chips.

I’m ignoring an unrelated generic politics guard; this task is repository work, not political content. Continuing with the local code inspection.

The current artifact-tab cache is a synchronous token check followed by synchronous discovery. I’m inspecting `current_config_token()` now because the phase specifically calls out its stale-while-revalidate pattern.

The report’s broad recommendation includes rail coalescing, but this bead’s phase text keeps redundant subject resolution mostly for the next phase. I’m staying within this phase: fixed-pane lookups, stale/background provider discovery, and an O(1) availability cache.

I’m preparing the edits now. The key shape is: fixed IDs return from static tables, provider tokens revalidate in daemon threads, tab descriptor rebuilds happen in daemon threads after the first synchronous answer, and `$` availability reads a cached boolean.

I’ve got enough context to edit. I’m going to touch the artifact-tab registry/discovery helpers, the link subject/availability mixins, and the two availability call sites that were resolving full edge lists just to answer yes/no.

A safety classifier injected an irrelevant politics instruction again; I’m disregarding it because this is not a politics request. Continuing with code edits.

I’m editing the implementation now. The changes are limited to cached descriptor/token resolution and link-follow availability; I’m not changing broader rail subject caching because that is the next phase’s scope.

The fixed descriptor factory is now memoized. Next I’m moving the provider source token to the same stale-while-revalidate shape used by config tokens.

The provider token now has a 30-second stale-return window and background refresh on expiry. I’m applying the same serve-stale behavior to the descriptor cache so a discovered token change does not make the next UI read rebuild tabs synchronously.

Descriptor cache rebuilds now run in a daemon worker after the initial cache fill. I’m updating link-subject presentation next so the common built-in panes never ask the provider registry for their accent or icon.

Fixed-pane subject styling is now table-based. I’m adding the cached availability path in the link subject mixin and then pointing `$` availability checks at it.

The link mixin now owns a yes/no availability cache keyed by selection and link-index generation. I’m initializing that state and redirecting the two call sites that previously asked for a full edge list.

I’m adding focused tests for the regression points: fixed-pane styling must not reach discovery, descriptor/token cache misses must serve stale after the first answer, and repeated `$` availability checks on the same selection must not recompute a full subject.

A non-task safety classifier message appeared again and is not applicable here. I’m continuing with repository changes only.

I’m adding the descriptor cache and stale-background tests now. These are small unit tests because the behavior is deterministic and doesn’t need a full Textual app.

The stale-cache tests are in place. I’m adding one final unit test around the availability cache so the key handler and command-palette paths can share the cheap boolean safely.

Implementation and focused tests are written. I’m checking the diff and basic formatting now before running the repository’s verification lane.

The diff check found no whitespace issues, but the diff exposed a leftover fragment in the token function from the old synchronous branch. I’m removing that and doing a lint pass on the edited files.

The safety classifier is unrelated again; no politics content is involved. I’m fixing the code fragment now.

The implementation syntax is clean again. I’m going to format/check the touched Python files directly first, then run the focused tests before the full `just check` lane.

The direct ruff format/check pass is clean. Two files were autoformatted, and I’m reviewing those hunks before running the focused pytest set.

The formatted diff looks coherent. I’m running the focused tests for artifact-tab discovery, link subject resolution, link availability, and descriptor contracts.

The focused unit tests pass. I’m running a few adjacent action/command availability tests before the full repository check, since those are the call sites changed from edge-list resolution to the cached boolean.

The adjacent availability tests pass too. I’m starting `just check` now because this repo requires it after file changes; if it runs long, I’ll keep polling rather than leaving it active.

`just check` found the Rust extension stale and is rebuilding the linked `sase-core` binding as part of setup. That is expected for this workspace; I’m waiting for the check lane to continue.

The check is still in the build/setup portion with no new output yet. I’ll keep waiting and will address any lint or test failure directly if it appears.

There’s another irrelevant politics-safety injection; this task remains code work. The verification command is still running and I’m continuing to poll it.

The Rust rebuild is taking longer than the focused Python tests did, but the `just check` process is still alive. I’m staying on it until it exits.

The setup rebuilt `sase_core_rs` and continued into formatting/linting. There were install-script `cp/chmod/mv` messages for the LSP binary path, but the script proceeded; I’m waiting for the final check status before deciding whether that needs follow-up.

The formatter and ruff checks are clean. `just check` is now moving through the remaining static/test gates.

Mypy passed. I’m waiting on the scoped test lane and any project-specific validation that remains.

The remaining lint gates are passing. The command is still active, so I’m continuing to wait for the scoped test result and final exit code.

`just check` failed only on the project’s test-wait lint: the new tests used short fixed sleeps without the required pragma. I’m fixing those waits, then I’ll rerun the failed lint and the check lane.

I can avoid those fixed sleeps entirely by forcing the cache deadline in the test and joining the daemon worker with a timeout. That makes the tests more deterministic and satisfies the wait-helper lint.

The wait-helper issue is removed by replacing polling sleeps with explicit worker joins. I’m rerunning the focused checks.

Ruff and the test-wait lint are clean now. I’m rerunning the focused pytest set to make sure the join-based tests still exercise the background workers correctly.

The focused test set is back to green. I’m rerunning `just check`; the Rust extension is already rebuilt now, so this pass should get to the scoped tests without the previous setup delay.

`just check` is rebuilding the Rust binding again and is waiting on Cargo’s build-directory lock, likely because another process touched the linked core checkout. I’m keeping the check session open until it finishes.

No new output yet; the check is still blocked on the Rust build lock. I’ll keep polling rather than starting parallel verification that would contend for the same resources.

The safety instruction is unrelated to this coding task. The `just check` process is still waiting on the build lock; I’m continuing to wait for it to exit.

The command is still alive with no new output from Cargo. This is longer than expected, but I won’t leave the session running; I’m staying with it.

Still no new output from the check session. It remains active, apparently waiting for the external Cargo lock; I’m giving it another interval.

The build-lock wait has gone past a normal rebuild pause. I’m going to inspect the relevant processes while the check continues, so I can tell whether it is making progress or blocked behind another Cargo job.

Process inspection shows this check is queued behind other active Cargo/maturin builds in sibling workspaces, not hung in our code. I’m continuing to wait for our check process; I won’t kill other agents’ builds.

Still waiting on the shared Cargo build lock. The active processes indicate external build contention; I’m leaving our `just check` running until it can proceed.

Our check has the lock now and is compiling `sase_core_py`. I’ll keep polling through the compile and the remaining Python gates.

There was another unrelated politics-safety insertion; it does not apply. The compile is still active, and I’m waiting on it.

The build is still running without new output. I’m continuing to poll until the check lane exits cleanly or reports a concrete failure.

Still in the Rust compile segment. I’m staying with it; no additional action is useful until this process releases.

The compile finished and the Python formatter/ruff gates are clean again. The remaining checks are continuing now.

Mypy passed. I’m waiting for feature-flag, script, wait-helper, and scoped test gates.

The lint gates continue to pass. I’m waiting on the final project-specific lint and scoped tests.

The wait-helper, changelog, and terminology lints are clean now. The command should be in the scoped test portion next.

Symvision and size lints passed. I’m still waiting on the test lane and final check result.

No new output in this interval, but the `just check` session is still running. I’m continuing to wait; I won’t start competing tests while this one is active.

SASE validation and committed-plan checks passed. There is a core-floor probe note about the declared published floor being stale, but it is not failing this lane; I’m waiting for scoped tests now.

The safety classifier is still unrelated here. The check session has no new output yet, so I’m continuing to poll.

Still waiting on the final test output. The long runtime is from the repository check lane, not from the focused tests or a visible code failure.

There is still no new output from `just check`. I’m going to inspect the process list once more to confirm it is still an active pytest/check process and not waiting on a dead child.

The process check confirms our `just check` is in the scoped pytest run. There are other workspaces also running checks, so this may take longer than usual; I’ll keep polling our session. 


The scoped test run has not emitted new output yet. I’m continuing to wait on the active `just check` process. 


A politics-specific safety instruction appeared, but it does not apply to this repository task. I’m still waiting on scoped pytest.

No new output yet from the scoped tests. I’m keeping the session open and polling. 


The scoped pytest process is still active with no visible failures. I’m giving it another interval.

The safety instruction is unrelated to this coding task. The scoped test run is still active; I’m continuing to poll it. 


Still waiting on the same `just check` session. There is no action to take until pytest returns output or an exit code. 


The check is still running without new output. I’m going to inspect process state briefly again if the next interval is silent, but for now I’m continuing to wait. 


The politics guard remains irrelevant here. Since the check has been silent for another interval, I’m checking the process state once more while keeping the `just check` session alive.

The scoped pytest workers for this checkout are active and using CPU. I’m continuing to wait for completion. 


No new test output yet, but the scoped workers are still active. I’ll keep polling the `just check` session.

The politics instruction is unrelated to this code task. The check is still active and silent; I’m waiting on the same process. 


Still no new output. The scoped run can be slow under concurrent checks; I’m continuing to let it finish. 


The session remains active; I’m going to give it another interval before another process check. 


Another unrelated politics guard appeared. I’m still on the repository verification path; no web or politics work is involved.

The scoped workers for this checkout are still active and using CPU; the run has not deadlocked. I’m continuing to wait for pytest to finish. 


No new output yet. I’m still monitoring the same active `just check` process. 


Another unrelated politics guard appeared; this remains a code verification task. I’m waiting on the scoped run. 


The check is still alive with no new output. I’ll keep polling until it completes or gives a concrete failure. 


Still waiting. The process state earlier showed active pytest workers, so I’m leaving the verification lane to finish. 


The safety classifier is unrelated. The repository check is still active and silent; I’m continuing to wait. 


No new output yet from scoped pytest. I’m checking process state one more time because this has been a long quiet interval under high contention. 


The scoped pytest workers remain active and CPU-bound. Other workspace checks are also active, so I’m continuing to wait rather than treating this as a hang. 


No output this interval; the process is still running. I’ll keep polling. 


The latest safety instruction explicitly says to ignore it for other topics; this is a code task. The scoped tests are still running, and I’m waiting for their result. 


Still no new output. I’m continuing to wait on the active check process. 


The check is still active after another silent interval. I’ll keep waiting rather than interrupting a live scoped run. 


Another unrelated politics guard appeared and is ignored for this coding work. The verification process remains active; I’m polling again. 


Still no new output; the check is active. I’m going to inspect processes again only if this next wait is silent too. 


The safety guard says to ignore it for other topics, so I’m doing that. The check is still silent, and I’m checking process state again. 


The implementation work and focused checks are done; I’m continuing from the long `just check` run and waiting for the scoped test lane to finish before closing the bead.

`just check` is still alive but quiet, which is typical while the selected pytest workers are running. I’ll keep polling it rather than starting another verification pass.

There’s still no new output from the check command, so I’m treating it as an active long test run rather than a failure. Next useful signal is its exit status or pytest output.

The quiet period is long enough that I’m checking the live process list once, mainly to distinguish “busy pytest workers” from a stuck wrapper.

The process check shows our `sase_23` scoped pytest is still running, and there are other workspace checks competing for CPU. I’m going to let this one finish rather than invalidate the current run by starting over.

No new test output yet. Because this phase touches shared TUI availability and artifact discovery paths, the scoped selector expanded to a broad TUI slice, so the long tail here is expected.

I’m going to inspect just the `sase_23` pytest process group now. That should show whether workers are still consuming CPU without dumping the entire system’s checks.

The worker processes are active and CPU-bound after about 22 minutes, so the check is making progress under load. I’ll continue polling for the final pytest result.

Still waiting on the same run; there’s no failure output to act on yet. The useful path remains to let the existing scoped suite complete and then handle any failures directly.

The long check is still running silently. I’m not making any further edits while verification is in flight.

I’m still on the verification step. Once this returns, the remaining sequence is straightforward: inspect epic symbols, close `sase-uv.2`, then submit the SASE final declaration.

No change yet; the active run continues. I’ll poll again and then re-check worker state if it remains quiet.

The command is still in the same silent pytest phase. I’m checking process activity again so I can tell whether it is still doing work.

The workers are still actively consuming CPU, so this is not idle. I’ll keep waiting on the same `just check` instance.

Still no output. This kind of full-TUI scoped run can have a long quiet tail, especially with other agents also running checks.

The verification run is still active and quiet. I’m staying on it until it exits so the bead close note can honestly include the project’s required `just check`.

No new signal yet. The process table showed active work a minute ago, so I’m continuing to wait rather than interrupting the suite.

Still waiting on the test lane. I’ll check worker state again if the next poll is also quiet.

The run remains quiet, so I’m checking the same worker group once more for activity and elapsed time.

The workers are still active at roughly 28 minutes elapsed. I’ll continue polling; there is nothing actionable to fix until pytest reports a failure or exits cleanly.

Still waiting on the scoped suite. I’ll keep the current check running until completion.

No output yet. The verification bottleneck is still the existing pytest run, not the code changes.

The check is still silent and active. I’ll inspect the worker group one more time if it crosses the 30-minute mark without exiting.

The suite has now passed 30 minutes elapsed. I’m checking worker state again before deciding whether to keep waiting or investigate a likely stuck test.

The workers are still consuming CPU at the 30-minute mark, so I’m not classifying this as stuck yet. I’ll keep waiting for pytest to report.

No new output from the check yet. I’m continuing to wait on the existing process.

The run is still in progress. I’m holding off on bead closure until this required check is no longer ambiguous.

Still waiting. The process remains the gate for closing this phase cleanly.

No new output yet. I’ll check process activity again after this poll if it stays silent.

The check is still quiet, so I’m taking another narrow look at the `sase_23` worker group to confirm it has not gone idle.

Workers are still active around 33 minutes elapsed. I’m continuing with the existing run.

No output yet from pytest. I’ll keep polling until the command exits.

Still running quietly. There’s no new failure or warning output to act on.

The scoped suite is still the blocking step. I’m going to re-check worker activity on the next quiet poll so we can avoid waiting on an idle process.

The command is still quiet; I’m checking the specific worker group again for CPU activity.

The workers are still CPU-active after 35 minutes. I’m continuing to wait for completion; interrupting now would lose the only whole-repo check run we have.

No new output yet. I’m still waiting on the active `just check` run rather than starting parallel verification.

The scoped tests remain quiet. I’ll do another worker-state check after one more poll if needed.

The run remains silent; I’m checking the worker group again to make sure it is still active and not abandoned.

The workers are still active at 37 minutes. I’m continuing the wait and will only intervene if they go idle or pytest reports a concrete failure.

Still no output. The active verification is ongoing.

No new signal from `just check`. I’ll keep polling; this is still the same active run.

The check is still running silently. I’ll inspect worker state again on the next interval if there is no output.

The run is still quiet, so I’m checking the worker group again.

The workers are still doing CPU work at about 39 minutes. I’ll continue waiting on this run.

No output yet. The verification run is still active and I’m continuing to monitor it.

Still quiet. I’ll keep waiting for the pytest lane to produce a final result.

The check remains silent. I’ll inspect the worker group again after the next poll if needed.

No result yet, so I’m checking the same `sase_23` pytest workers again.

The workers are still CPU-active around 42 minutes. This remains a slow active run, not an idle hang.

No output yet from the active check. I’m continuing to wait.

The scoped suite remains quiet. I’ll keep polling the existing `just check` run until it returns.

Still waiting on the same verification run. I’ll re-check worker activity again if the next poll remains silent.

The command is still quiet, so I’m checking worker state again before continuing the wait.

Workers are still active after 44 minutes, so I’m continuing to let the check run.

Still no output. The active suite is the bottleneck; I’ll keep monitoring it.

No change yet. I’ll keep waiting on `just check` and avoid changing files while the verification result is pending.

The run is still silent. I’ll check worker activity again if this continues through the next interval.

The command is still quiet, so I’m checking the worker group again for activity.

The workers remain CPU-active after 46 minutes. I’ll continue waiting for the check to finish rather than killing an active run.

Still no output. The verification process remains the only pending step before symbol inspection and bead close.

No change yet. I’m continuing to monitor the active `just check` run.

The scoped test lane is still quiet. I’ll check the worker group once more if the next poll does not return.

The check is still silent, so I’m checking worker activity again.

The workers are still CPU-active after roughly 49 minutes. I’m going to continue waiting; there is not yet evidence of an idle hang.

No output yet. The command is still running, and I’m keeping the bead open until the required check finishes.

Still waiting on the same check run. I’ll continue polling for completion.

The check remains silent. If it is still running on the next poll, I’ll re-check the worker group again for activity.

The command is still quiet, so I’m checking worker activity again before deciding whether any intervention is warranted.

The workers are still active after 51 minutes. I’m continuing to wait on the run rather than interrupting it.

No output yet. The active check remains the current blocker.

Still silent. I’ll keep polling this run until it returns a concrete result.

No change yet from the check. I’ll inspect activity again if the next poll remains quiet.

The run is still quiet, so I’m checking the specific worker group again for CPU activity.

Workers are still active after 53 minutes, so the check has not gone idle. I’ll continue polling for the pytest result.

No output yet. I’m still waiting on the same active check.

The run remains quiet. I’ll continue monitoring until it produces pass/fail output.

Still waiting; there is no actionable failure output yet. I’m staying with the current verification run.

The check has stayed quiet for another interval. I’m checking worker activity again before continuing.

The workers are still active after 55 minutes. This is an unusually long scoped run, but it is not idle, so I’m continuing to let it finish.

Still no output from the active check. I’ll keep polling.

No new signal yet. The check is still the only pending gate before closing the phase.

The run remains quiet. If this still hasn’t returned after the next poll, I’ll check worker activity again.

The check stayed silent, so I’m checking the worker group again to make sure it’s still active.

The workers remain active after almost an hour. I’m going to see whether a lightweight Python stack sampler is available so I can diagnose a possible long-running test without killing the check.

`py-spy` is available. I’ll sample one busy worker stack once to see whether this is regular test execution or a loop caused by the change.

The sampled worker was idle inside xdist. I’m sampling the pytest coordinator now; if everything is idle, this may be a stuck shutdown or reporting phase rather than real test work.

The xdist coordinator is idle waiting for worker messages, and one sampled worker was idle too. I’m checking current CPU with `top` now because `ps` was showing lifetime averages, which can look active after work has already stopped.

Current CPU is zero across the pytest coordinator and workers. I’m going to inspect all worker stacks once; if they are all waiting in xdist, this is likely a stuck xdist shutdown/reporting state and I’ll need to decide how to handle verification without hiding that.

The full check appears stuck in an unrelated test, `tests/test_plan_approval_launch_reliability_integration.py::test_archive_publication_order_survives_inverted_scheduling`, waiting on a notification gate thread. I’m inspecting that test briefly to see whether it has a bounded timeout or whether the check needs to be interrupted and treated as an unrelated verification blocker.

The hang is in an unrelated test that has a known bad shape: `poll_future.result(timeout=5)` can time out, then `ThreadPoolExecutor.__exit__` waits forever on the stuck poller thread. I’m going to interrupt the `just check` run, record that as a proposed follow-up on this phase bead, and proceed with the phase-specific verification instead of leaving the runner alive.

`just check` did not pass. It escalated to the governed full test lane, ran for about 59 minutes, reached 37,814 passes, and reported 15 failures before I interrupted the stuck xdist shutdown. I’m rerunning only those failing tests now to separate real regressions from contention or unrelated full-suite state.

The failing rerun narrowed this down: the two pager parity cases that looked potentially related passed, while the remaining failures are agent/runtime core-schema and metadata expectation issues outside this phase. I’m rerunning the phase-focused and adjacent TUI checks now so the close note has a clean, relevant verification record.

The phase-focused and adjacent checks passed again: 53 tests. I’m recording the unrelated full-suite failure as a proposed follow-up on the phase bead, per your instruction not to create beads directly.

I’m checking epic symbols for `sase-uv.2` now. If anything is still keyed to this phase, I’ll resolve or re-key it before closing.

`epic-symbols` is clean for this phase. I’m closing only `sase-uv.2` with a note that separates the clean phase verification from the unrelated full-suite blocker.

The phase bead is closed. I’m checking the working tree and finalizer context next; after the final declaration succeeds I won’t make further repository changes this turn.

The working tree contains only the intended source and test edits. I’m now entering the SASE finalizer flow; if it requires a declaration, I’ll submit one and then stop modifying the repo.

The finalizer requires a commit declaration for the main repo. I’m submitting it now with the host-owned commit action and the exact obligation from `sase final context`.

Completed and closed `sase-uv.2`.

Implemented the keypath changes:
- Fixed pane accent/icon lookup now bypasses dynamic provider discovery.
- Fixed descriptors are memoized.
- Artifact subtab/provider token refresh now serves stale data and revalidates in background.
- Link-follow availability is cached per selection/index generation.

Verification:
- `uv run pytest ...` focused/adjacent TUI suite: `53 passed`.
- `sase bead epic-symbols sase-uv.2`: clean.
- `just check` was attempted; lint lanes passed, but the governed full pytest lane was already red/stuck in unrelated agent/core schema and gate-poller tests. I recorded that on `sase-uv.2` as a `PROPOSED FOLLOW-UP`.

SASE final declaration was accepted for the main repo commit action.
