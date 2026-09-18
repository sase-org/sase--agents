# Chat History - ace-run (sase-11l.6)

- **TIMESTAMP:** 2026-09-18 08:16:21 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-11l.6

## Prompt

#gh:gh_sase-org__sase
%id(6, clan=sase-11l, bead=sase-11l.6)
%model:@medium
%auto
%w(bead=sase-11l.5)
Can you complete the work for bead sase-11l.6? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-11l.6 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-11l.6`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-11l.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I’ll pick up the bead in the project’s own workflow: first I’m going to read the bead/memory instructions so the close-out doesn’t leave stale epic symbols behind.

I’m using the SASE memory-read path here because bead lifecycle rules are audited project memory, and this bead has explicit close semantics.

I’ve got the lifecycle rules. Next I’m reading the bead itself and nearby project state so I can find the design file and the exact implementation surface.

The bead points at `plan:202609/hold_directive.md` under the SASE plans checkout, so I’m going through the repo access instruction before opening that design file.

I’m going to open the plans checkout via `sase repo`, then read only the phase-relevant parts of the design.

The plans sidecar opened cleanly. I’m reading the `%hold` design now, with an eye for the phase’s exact acceptance criteria and any symbol handoff notes.

The phase is specifically about `%hold` completion and LSP parity. The plan also requires the research artifact for every phase, and this work touches xprompt/directive and ACE TUI code, so I’m pulling those reference notes before editing.

The design says all phases should consult the reverse-wait research report, so I’m doing the audited artifact read before touching code.

The artifact read didn’t resolve even though it printed a candidate path, so I’m going to inspect the registered repo/artifact names rather than bypass the audit trail.

The artifact exists in the index but the research sidecar is not present in this workspace. I’m opening that sidecar through `sase repo`, then I’ll retry the audited artifact read.

The research checkout is now present; I’m retrying the audited read instead of opening the Markdown file directly.

The accepted design is clear: this phase is shared editor contract plus ACE/LSP parity, not runtime hold behavior. I’m opening the linked Rust core now because the completion contract lives there.

I’ve opened `sase-core`. Now I’m mapping the current `%hold` and `%wait` completion implementation on both sides so the change follows the existing contract instead of inventing a parallel path.

The broad search confirmed prior phases have already landed `%hold` runtime pieces. I’m narrowing to the completion contract, candidate builders, and parity tests now.

There’s already a `%hold` directive row and scope completion, but the Hood role and richer target rows are not finished. I’m reading the precise structs/tests so I can make the smallest compatible wire change.

The wire struct still documents only agent/family/clan/tribe, and completion treats unknown kinds as agents. I’m checking the existing sorting/filtering tests so hood rows fit naturally.

The ACE facade currently funnels all agent-role clauses through wait-style filtering, which is why `%hold` is still losing proc rows. I’m checking how the helper builds catalog rows so hood rows can be available to both ACE and LSP.

The helper currently emits agent rows plus family/clan/tribe aggregates; no hood aggregates yet. I’m reading those aggregation helpers and the LSP server tests before editing.

I found the important split: the core wait builder also needs to understand `proc` as its own kind, otherwise LSP can’t make wait-only exclusions and hold-only inclusions consistently. I’m reading those builders before patching.

The contract already has `DirectiveValueRole::Hood`; it just wasn’t dispatched. I’m going to patch the Rust completion layer, the Python ACE candidate splitter, and helper/parity fixtures together.

Before editing, one more small check: I’m seeing how ACE delegates to the Rust binding for static rows so I don’t duplicate keyword/scope behavior unnecessarily.

I’m making the completion layer understand `hood` and `proc` as first-class target kinds, and adding hold-specific candidate assembly so `%wait` and `%hold` can diverge cleanly.

The first patch missed a slightly different import layout in `completion.rs`, so I’m splitting the edits into smaller patches against the actual file shape.

I’m applying the Rust core changes first, then I’ll do the Python surface after that compiles logically.

The core dispatcher now routes `%hold` and `hood=` separately. Next I’m refactoring the candidate builder just enough to support wait-excludes-proc and hold-includes-proc with pre-run ranking.

The wait builder now filters proc rows. I’m adding the hold builder and the hood synthesis helper in the same local cluster.

Now I’m teaching the shared row logic about the new target kinds and deriving hood candidates from existing agent names when the helper has not precomputed them.

The core can now emit hood and proc rows distinctly. I’m updating the LSP label/kind projection so those rows are displayed and sorted consistently.

The Rust side is in place. I’m moving to ACE now: generalizing wait-style parsing to include `%hold`, then giving hold its own target builder so proc rows aren’t filtered out.

ACE target completion is getting a small extension: derive hood rows from visible names, preserve proc rows for `%hold`, and keep `%wait`’s proc exclusion intact.

ACE’s facade now has a hold-specific path. I’m adding hood/proc rows to the editor helper catalog so LSP gets the same live inventory shape.

One subtlety surfaced: hood rows belong under `hood=`, not bare `%hold(...)` positional targets. I’m excluding hood rows from positional hold targets while keeping them for the keyword value.

Now I’m updating the parity fixtures to include hood and proc rows, plus surface normalization so ACE and LSP compare the same rendered details.

The fixtures now carry `WAITING`, `QUEUED`, `hood`, and `proc` rows. I’m adding explicit parity checks for hold positional targets and `hood=` values.

I’m adding a small core-side assertion too, so the Rust contract itself proves wait excludes proc/hood while hold includes proc and handles hood values.

I’ve picked up the phase work midstream. I’m going to firm up the changes with formatting and targeted checks, then I’ll clear the bead’s epic symbols and close only `sase-11l.6` once the tree proves out.

The primary workspace has the expected Python/test edits. The core checkout path wasn’t where the compacted summary guessed, so I’m re-opening the linked repo through SASE before touching it again.

Core is at the linked checkout under `sase/repos/linked/sase-core`. I’ll verify the diff shape there, then format both sides before running the focused tests.

The implementation shape matches the plan: Rust owns the new `%hold` completion semantics, ACE mirrors it, and LSP display/sort mapping knows about `hood` and `proc`. I’m checking the local test scaffolding now so I can add the narrow Rust coverage instead of relying only on Python parity.

There are existing test clusters for both core completion and LSP conversion, so I’m going to patch into those. The earlier search was a bit chatty, but it did point me at the right neighborhoods.

The core tests have helpers for exactly this sort of directive argument completion, and LSP conversion already has a compact kind/sort test. I’m adding coverage there now for `%hold` targets, hood value completion, and the new LSP item kinds.

I’m about to make the test patch in the linked Rust core. It’s intentionally small: no behavior changes now, just assertions that the new completion contract survives future edits.

Now I’m updating the LSP conversion assertion so `hood` and `proc` get locked to their intended icons/sort buckets, rather than being treated as generic agent values.

The LSP test has slightly different formatting than the patch context expected. I’m reading the exact block and then I’ll apply the same change against the real shape.

Found it. Applying the LSP test update against the exact block now.

The conversion helper already avoids duplicate labels when the detail begins with the normalized kind, so I’m tightening the new assertion to match the polished display text.

The Rust-side assertions are in. I’m moving into formatting now, then I’ll run focused Rust and Python parity tests before the full project check.

Rust formatting completed cleanly. I’m formatting the Python workspace next, which may also normalize import ordering in the touched test files.

Formatting touched two Python files, which is normal after ruff. I’m checking the resulting diff before tests so any formatter-driven reshuffle doesn’t hide a real issue.

Diff size is reasonable: three Rust files plus the ACE/parity surface. I’m starting with the narrow Rust tests that exercise the new completion behavior and LSP conversion.

The first Cargo run is compiling and the other two are queued behind Cargo’s build locks. That’s fine, just less elegant than hoped; I’ll let them drain instead of starting more work on that target directory.

The first Rust test hit a straightforward test-only name shadowing bug: my local `entries` vector hid the `entries()` helper. I’m stopping the queued Cargo runs, fixing that, then I’ll rerun the focused suite sequentially.

Cargo has exited cleanly from the failed compile now. I’m renaming those test locals so the helper stays callable.

That rename was a little too surgical-looking, so I’m reading the patched block to make sure both inventory fields use the new local name.

One inventory field was still pointing at the wrong name. Fixing that now before retrying the Rust tests.

The test helper names are clean now. I’ll re-run Rust formatting quickly, then run the tests sequentially to avoid the build-lock pileup.

Rust formatting is back to clean. Starting the focused tests again, one at a time this round.

The compile errors show my broad text patch accidentally touched an earlier existing test’s `entries` local too. I’m going to repair those locals explicitly rather than letting search/replace be clever.

Cargo is still draining after reporting those compile errors; once it exits I’ll apply the exact repair.

The failed Cargo process is done. I’m reading the affected test region and then I’ll make a precise fix.

I found all of the fallout: earlier tests now had `agent_entries` locals but still called `&entries`. I’m aligning those references and renaming the new hold local so `entries()` remains available.

There were two more swapped names in adjacent tests. I’m restoring the wait test’s original local and keeping the hold test on `agent_entries`.

I’m doing one more exact read because loose patches in a dense test block are not worth trusting.

The read caught the two exact mismatches. This time I’m patching with surrounding function context so it won’t hop to a neighboring test.

The test locals are coherent now. I’ll format and retry the focused Rust checks.

Formatting is quiet. Re-running the first focused Rust test.

The core test is compiling now; no immediate compile errors this time.

Still building. I’ll keep waiting this one out before starting the next test.

Good, the `%hold` target-order/proc inclusion core test passes. I’m running the hood value derivation test next.

The hood derivation test exposed that `agent_name_ancestors` includes the full dotted name as one of the addressable prefixes. That may be intentional for hood semantics, so I’m checking the identity helper before deciding whether to filter it or adjust the expectation.

I found the identity helper. I’m reading its tests because they encode the intended ancestor list better than a guess would.

The identity helper’s own tests say the full dotted family is an ancestor too, so deriving both `sase-abc` and `sase-abc.1` is intended. I’m adjusting the assertion to match that contract.

The core test expectation now matches the identity contract. Formatting and rerunning the remaining focused Rust tests.

Retrying the hood derivation test.

The hood test is recompiling after the assertion edit.

Still building. The core crate is hefty, but the actual test should be quick once it links.

The hood value derivation test passes now. I’m running the LSP conversion test for the `hood` and `proc` item kind/sort mapping.

The LSP crate is compiling its dependencies now; I’ll let that finish before moving into the Python parity layer.

Still linking/building the LSP test target. No new errors yet.

Focused Rust checks are green. I’m checking how the Python parity harness launches the LSP so I can make sure it sees the freshly changed Rust code.

The parity harness launches `sase-xprompt-lsp` from the venv’s bin directory, so I need to install/build the updated local Rust artifacts before running that test. I’m checking the repo’s install/check recipes now.

The Justfile has a local-dev install path and a dedicated Rust install path for both `sase_core_rs` and `sase-xprompt-lsp`. I’m reading those recipes to pick the smallest correct rebuild.

The parity tests need both updated pieces: Python calls into `sase_core_rs`, and the LSP harness runs the installed `sase-xprompt-lsp`. The repo has `just rust-dev-install` for exactly that, but it may try to refresh the linked checkout, so I’m checking that helper before running it over a dirty core tree.

To protect the dirty linked core checkout, I’ll run the dev Rust install with `SASE_ALLOW_STALE_CORE=1`, which skips the checkout refresh and builds the venv artifacts from the current working tree.

The dev Rust install is building the Python extension now. This is the slow but necessary step so ACE, LSP, and the parity harness all read the same core contract.

It’s into `sase_core` now. I’ll keep waiting; no failures have surfaced.

Still compiling. The next visible phase should be the PyO3 extension finish, then the LSP binary build/install.

Still waiting on the Rust install. It’s quiet, which usually means the compiler is chewing through the larger crate.

The extension build has moved on to `sase_gateway`, so progress is real. I’m letting the install continue.

Now it’s compiling the Python binding crate itself. After this, it should copy the extension into the venv and build the LSP binary.

The Python extension installed successfully and the LSP build has started. Letting the final binary build/copy complete.

The LSP build is still running. No errors so far.

The LSP build is into `sase_core`; it should be on the same source we just installed into Python.

Still compiling the LSP target. I’m continuing to wait; this is the last install step.

Now it’s on the final LSP crate. Should be close.

The venv now has the rebuilt `sase_core_rs` and `sase-xprompt-lsp`. I’m running the directive completion parity test module next, since that exercises ACE and LSP against the same sample catalog.

Parity found two real mismatches. First, my Rust refactor accidentally alphabetized same-kind `%wait` agents while ACE preserves catalog order. Second, LSP isn’t fetching the agent catalog for `hood=` value completion yet. I’m fixing those at the Rust layer.

I found the LSP catalog gate. It already lists agent/clan/family/tribe, and just needs `hood` added. I’m patching both the catalog gate and the stable sort behavior now.

I’m applying two Rust fixes: keep sort stable within same status/kind groups, and include `DirectiveValueRole::Hood` in the LSP agent-catalog gate. I’ll also extend the existing LSP server test to cover hood value rows.

One subtlety: `%hold` is feature-gated, so I’m checking whether the LSP unit test helper has a way to enable `agent_holds` before I rely on `%hold(hood=...)` there.

The LSP unit test needs the same hold flag that the parity harness sets. I’m enabling `agent_holds` on that test server without disturbing the rest of its default config.

The flag gate and stable sort patch are in. I’ll format Rust and rerun the targeted Rust tests that cover these paths.

Running the core hold/wait focused tests after the sort fix.

I accidentally let two Cargo tests contend for the build lock again. I’ll let this pair drain, then keep subsequent Rust runs single-file.

Both are still in Cargo’s build pipeline. No errors yet.

The core hold and wait tests are green after the stable-sort fix. I’m running the LSP server test that now includes `%hold(hood=...)`.

The LSP server test is compiling against the changed core.

Still compiling the LSP test target.

The LSP test did fetch the catalog now, and the empty `hood=` token correctly offered every explicit/derived hood. I only meant to assert the `s`-filtered case, so I’m tightening the test token to `%hold(hood=s`.

I’m formatting and rerunning that LSP server test with the prefix-filtered hood token.

Re-running the LSP server contract test.

The Rust fixes are green. Since both the Python extension and LSP binary changed again, I need to refresh the venv artifacts once more before rerunning Python parity.

The second dev install is incremental and already compiling just the changed core.

Still building the updated extension.

Still waiting on the incremental Rust install; no errors yet.

The Python binding crate is compiling now; after it installs, the LSP binary rebuild should be quick.

The updated Python extension is installed; LSP rebuild is underway.

Still building the LSP binary.

No output yet; waiting for the final LSP install line.

The venv artifacts are refreshed. I’m rerunning the full directive completion parity module.

Parity is down to one display-detail mismatch: LSP-derived hood rows include `hood · 1 member`, while ACE-derived hood rows had empty detail. I’ll make ACE derive the same hood detail so the surfaces match.

ACE candidates don’t carry a freeform detail field on the agent metadata, so the parity surface computes display details from the group metadata. I’ll teach that surface helper to render aggregate hood/family/clan/tribe counts the same way core/LSP does.

I’ll keep the production ACE model unchanged and normalize the parity surface from the metadata ACE already has. For derived hood rows, `member_count` is present, so the test surface can render `hood · N member(s)` just like core/LSP.

That’s a tiny test-surface change. I’ll run the formatter, then rerun the parity module.

Formatting is clean. Re-running parity now.

The parity surfaces now match. The remaining failure is my too-narrow assertion: `ship` is a valid derived hood prefix for `hood=s`, alongside explicit `sase-11l`. I’m updating the expected insertions.

That assertion change doesn’t need much, but I’ll run formatting and the parity module once more.

Formatting is still clean. Running parity again.

Parity is green. I’m going to re-run the remaining focused Rust assertions touched earlier, then move on to the required full `just check`.

The hood derivation core test still passes. Running the LSP conversion assertion too.

Focused Rust and parity checks are green. I’m checking the worktree shape, then I’ll run the required `just check` with the linked core refresh disabled so the dirty cross-repo changes stay intact.

The diff is scoped to `%hold` completion support in core/LSP plus ACE parity plumbing. Running `just check` now; this may take a bit.

`just check` is underway and has passed formatting, keep-sorted, and ruff. It’s moving into the heavier lint/validation stages now.

No new output yet; likely mypy or validation is running under the silent wrapper.

Mypy passed. Continuing through the remaining project checks.

Still running; the silent wrapper only prints stage results as each one finishes.

Feature-flag lint passed. The check run is still moving.

The script/test-wait/changelog terminology lints are green too. Waiting on the remaining validation and scoped tests.

Still running. It’s probably in symvision or validation now.

No new stage output yet. I’m continuing to wait; this still looks like a normal long check stage.

Symvision and toobig passed. The run is into SASE validation/scoped tests next.

Still running validation. No failure output yet.

SASE validation passed; the core-floor probe emitted an advisory about the published floor but did not stop the check. Continuing into the remaining stages.

Still running. Likely scoped test selection/execution now.

Still quiet; waiting on the scoped tests.

No output yet. This stage can be a little patient-testing, but still no sign of failure.

Still waiting. I won’t start anything else while the full check owns the workspace.

The check run is still quiet. I’ll keep polling until it finishes rather than leave a live process behind.

Still no output from the silent stage; this is long but not stuck enough to interrupt. Continuing.

Still running. The lack of failure output is good, even if the suspense is not the fun kind.

Still waiting on `just check`; I’m staying with it.

This is now the long silent part of the check. I’m going to peek at the process tree in a separate read-only command so we know what it’s doing, while leaving the check itself alone.

That process-tree peek didn’t catch the tool process because the session id is not an OS pid. I’ll query by command name instead.

The process query shows our workspace is in `just test-scoped` with pytest workers, so the silence is expected. I’ll keep waiting for the scoped run to report.

Scoped tests are still running.

Still waiting on scoped tests.

Still no final result from `just check`; it’s still alive.

This scoped test run is taking a while. I’m going to peek once more at active pytest workers to confirm it’s still making progress.

The scoped pytest master is still running. I’m checking its child processes; if there are active workers, I’ll just keep waiting.

There are six active pytest workers, so the scoped run is genuinely busy rather than wedged. Continuing to wait.

Scoped tests still running.

Still in scoped tests.

Still waiting; the worker set is likely chewing through the selected suite.

No result yet. I’m keeping the turn open until this finishes.

It has been quiet long enough that I’m checking the worker states again, just to catch any stalled process early.

Workers are CPU-active, so the run is still progressing. Continuing to wait.

Still running.

Still no final line from `just check`.

Still in the scoped suite. Long, but active.

Still waiting. I’m not going to interrupt a healthy `just check`.

Still running.

The scoped suite is still active. I’ll keep checking in until it returns.

Still no output. This is the longest part of the turn; I’m staying with it.

Still running.

The check process is still alive. I’m polling again.

Another quick worker-state check, because this has been quiet for a long stretch.

Workers are still consuming CPU, so this is slow rather than stalled. Continuing.

Still running.

Still no final output from the scoped run.

Still running.

Still in the scoped tests. I know this is a long one; I’m staying on it.

Polling again.

Still running.

Still waiting on `just check`; no failure output.

One more worker-state check; at this length I want to make sure we still have active CPU, not a dead wait.

The workers are still CPU-active after 20 minutes, so this is not idle. Continuing to let it finish.

Still running.

Still waiting.

Still no final output.

Still running.

Still in the scoped suite.

Still running; I’ll keep polling.

Still no result from `just check`.

`just check` ran the full non-visual suite because the core identity path changed. All 42,793 tests passed, but the suite failed its temp-leak guard because `/home/bryan/.cache/sase/tmp/usage-probes` appeared. I’m going to inspect that leak source and decide whether it’s cleanup/rerun noise or a real follow-up.

The leaked entry is an empty `usage-probes` directory. The source already uses `get_sase_managed_tmpdir("usage-probes")`, so this looks like a known managed temp bucket that the guard nonetheless reports when full-suite selection runs. I’m reading the reaper/guard behavior to see whether the right fix is cleanup or whitelist alignment.

The leak is an empty bucket created by managed tmp usage, not files left behind. Because `usage-probes` is already a known managed tmp bucket in the reaper, I’m checking the test guard’s ignore model before deciding whether to add it there or file it as unrelated.

The guard expects `get_sase_managed_tmpdir()` to redirect into the pytest sandbox, so `usage-probes` appearing under the unsandboxed root means a child process probably lost the pytest redirect env. I’m checking the path helper and worker env propagation.

The path sandbox is keyed off `SASE_PYTEST_SANDBOX_DIR`, not just `TMPDIR`. I’m locating where tests publish that env; if usage-probe subprocesses scrub it, that explains the empty unsandboxed bucket.

The sandbox env is published by test fixtures, and `worker_environ()` allows `SASE_` names, so the leak likely comes from a test deliberately deleting `SASE_PYTEST_SANDBOX_DIR` around a usage probe or spawning outside the fixture. Since this is out of scope for `%hold`, I’ll record it on the phase as a proposed follow-up rather than patch unrelated temp-guard behavior.

I’m going to record this as a proposed follow-up on the phase bead, per your instruction, because the full-suite run exposed a temp-leak guard issue unrelated to `%hold`: an empty `usage-probes` managed-tmp bucket can be created under the unsandboxed root during usage-probe tests.

The bead note command is still running, likely touching the bead store. I’m waiting for it to return before moving on.

I’ll rerun `just check` now. Since the empty `usage-probes` bucket already exists, the temp-leak guard baseline should include it; this rerun should tell us whether there are any actual regressions left.

The rerun is already through mypy. I’ll keep polling through the full scoped test lane again.

Still running.

Feature-flag lint passed again. Continuing.

The script/test-wait/changelog terminology lints are green again. Continuing.

Still running.

Still in the silent validation/lint stage.

Symvision and toobig passed again. Waiting on validation and scoped tests.

Still running.

SASE validation passed again. The rerun is now entering scoped tests.

The core-floor advisory repeated but remains advisory; committed plans passed. Now the long scoped test lane starts.

Scoped tests are running again.

Still running.

Still quiet in scoped tests.

Still running.

Still running; same full-suite lane as before.

Still waiting on scoped tests.

Still running.

Still no scoped-test output yet.

Still running.

Still in the long test lane.

Still running.

Still waiting.

The rerun of `just check` passed. The scoped lane selected 418 files and completed green. Next I’m doing the required `sase bead epic-symbols sase-11l.6` check before closing.

No stale epic-symbol entries remain for the phase. I’m doing one final status check, then I’ll close only `sase-11l.6` with the verification note.

The final worktree contains only the intended primary and linked-core files. Closing `sase-11l.6` now with the verification summary.

The phase bead is closed successfully. I’m doing the required SASE final declaration next, then I’ll summarize the changes and verification.

The final declaration requires a manifest for every repo I changed. I’m fetching the host final context now and will submit the commit decisions right after.

I have the final context. I’ll declare both repositories for host commit: close the bead on the primary repo decision, keep it on the linked core decision, since the primary repo owns the assigned bead close.

The final submit rejected `bead_action: close` because the bead is already closed by the required explicit `sase bead close` command. I’m refreshing the final context and will resubmit with the repository commits while leaving bead state untouched.

The refreshed final context still requires commit decisions. Since the bead is already closed, I’ll submit both repository commits with `bead_action: keep` so the finalizer doesn’t attempt a second close.

Completed and closed `sase-11l.6`.

Implemented `%hold` completion parity across Rust core, LSP, and ACE:
- `hood` value-role completions with explicit and derived hood rows.
- `%hold` target rows with `WAITING`/`QUEUED` prioritization.
- Proc rows included for `%hold` but still excluded from `%wait`.
- ACE wait-style parsing generalized for `%hold`.
- Editor helper catalog now includes hood/proc rows.
- Parity and Rust tests updated.

Verified:
- Focused Rust core/LSP tests passed.
- `pytest tests/test_xprompt_directive_completion_parity.py -q` passed.
- `SASE_ALLOW_STALE_CORE=1 just check` passed.
- `sase bead epic-symbols sase-11l.6` reported no entries.
- Closed bead with the requested `sase bead close ...`.

I also recorded one unrelated `PROPOSED FOLLOW-UP` on the bead for a temp-leak guard issue surfaced during the first full-suite run. Final declaration was accepted for host commit handling.
