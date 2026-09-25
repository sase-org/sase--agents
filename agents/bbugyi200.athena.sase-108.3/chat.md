# Chat History - ace-run (sase-108.3)

- **TIMESTAMP:** 2026-09-13 12:26:19 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-108.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-108, bead=sase-108.3)
%model:@medium
%auto
%w:sase-108.1,sase-108.2
%w(bead=sase-108.1)
%w(bead=sase-108.2)
Can you complete the work for bead sase-108.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-108.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-108.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-108.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I’ll use the SASE bead/memory instructions first so I handle the phase bookkeeping cleanly, then I’ll inspect `sase-108.3` and its design notes before touching code.

The bead skill path listed in the session didn’t exist at the expected location, so I’m checking the skills directory layout and will keep following the SASE bead memory rules directly.

I’ve got the bead lifecycle note loaded. Now I’m reading the phase itself, looking for its linked plan/design file, and checking the repo state so I can separate this work from anything already in the tree.

The phase is specifically about making pager refs location-aware end to end: core ratchet, Python adapter, ACE fast path, copy behavior, corpus coverage, and a pilot navigation test. I’m opening the plan next so the implementation matches the intended phase boundary.

The first half of the plan confirms this phase depends on the prior core and landing phases, and `epic-symbols` is already clean for `sase-108.3`. I still need the rest of the phase checklist and then I’ll trace the resolver/copy paths.

This codebase already has the landing mark pieces from the prior phase, including `scroll_end_line` and navigation tests. I’m now narrowing to the remaining seams: the new core binding adapter, resolver split point, ACE LinkIndex fast path, copy text, and the rendered-link corpus.

I found the duplicate Python line suffix parser still in `_resolve_path_search.py`, which is exactly the thing this phase is meant to remove. The resolver still parses typed refs before stripping locations, so the next edit will introduce a Rust-backed location split and route everything through it.

The Python side has no `split_link_location` binding yet, so I need to inspect the linked Rust core checkout to see what commit the earlier phase produced and what binding name/version is now available. I’ll use the repo skill before touching that sibling checkout.

The repo skill is loaded; I’m opening/listing the linked repositories now so I can use the audited path rather than guessing where the core checkout lives.

`sase-core` is a linked repo and the current pin is `ba651fe...`. I’m opening the linked checkout with an audit reason, then I’ll compare its HEAD/bindings with the pin before editing the Python repo.

The project inventory reports `sase-core` in the listing, but `sase repo open sase-core` rejected it for this project key. I’m using the external GitHub repo identifier that the inventory also lists, which still gives us an audited local checkout.

I have the audited core checkout path now. I’m checking whether the Rust phase commit is present there and which exact revision should be pinned.

The core checkout’s HEAD is the expected `feat(artifact-ref): add the one link-location grammar`, one commit after the current pin. That gives this phase a concrete ratchet target: `17947a05ffd6aea9555a8498f42da0777229b8ea`.

The existing rendered-link corpus is nicely set up for this phase; it has real fixtures and checks copy/edit/navigation behavior. I’m going to extend that rather than build a separate mini-harness.

The validator only requires the older artifact-ref bindings today, so the ratchet would otherwise pass even if the new split binding disappeared. I’ll add the new binding names to the tool and its contract test as part of the adapter work.

The Rust wire shape is simple: `{schema_version, base, location: {line, column?, end_line?}}`. I’m going to add a small Python model module for that, then adapt resolver inputs before the existing branches.

One subtlety in the helper: the design says “regular file” but also says the helper must do no I/O. I’m going to avoid filesystem probes in the helper and rely on the target shapes produced by the existing resolvers, keeping directory/card behavior unchanged where those builders don’t carry a real line-oriented file landing.

The corpus extension needs one more fixture root for a configured document kind, so the scanner can prove custom sidecar-style refs keep their line suffixes too. I’m checking how known kinds get frozen into pager documents before I thread that through.

Known kinds are discovered from the document link context, and the corpus monkeypatch already feeds that context. I can add a `designs:` document root there and it should flow into both scanning and resolution.

For the pilot navigation piece, I’m going to assert the actual screen state after following a `plan:...:12-14` link: the document changes, the mark records 12 through 14, and the scroll position lands at the same reading offset used by the goto phase.

The existing navigation tests already expose the scroll expectation helper, so the new pilot can use the same `LineMark` and `reading_scroll_y` checks rather than brittle screenshot text.

I’ve got enough context to edit. I’m making the core pin and Python adapter changes first, then I’ll move the resolver over to location-first behavior and adjust tests around the new contract.

That first combined patch didn’t apply cleanly because the public facade export order differs from what I expected. I’ll split it into smaller patches against the exact local ordering.

Nothing was written by the failed patch, so the tree is still clean. I’m applying the same edits in smaller chunks now.

The revision pin and link-location wire/model types are in place. Next I’m exposing them through the existing artifact-ref facade and adding the Rust binding schema gate.

The operations module has a tighter import list than the facade, so I’m patching those exact sections now.

The model facade and operation wrapper are now patched. I’m exporting the same API through `sase.artifact_refs` so callers can use the stable facade.

The stable facade now exposes `split_link_location`. I’m adding the small pager helper that applies a parsed location to an already-resolved target, without doing any filesystem work.

Now I’m moving `resolve_link` to split before dispatch. Typed refs will resolve the base first, and only retry the whole original ref if the base fails and the old payload might have been legitimate.

Next I’m removing the old Python line suffix grammar from the path-search layer. After this, path search only resolves the base path and heading fragments; line/column/range comes from Rust.

With path search simplified, I’m updating the file-path resolver and copy path to split locations first, resolve the base, and append `:line[:column]` only for copied file paths.

The copy path now preserves line and column for file-path copies while leaving artifact refs verbatim. I’m trimming the fragment resolver next so Markdown headings are the only Python-side fragment lookup left.

Now I’m changing the ACE LinkIndex fast path to split first too, so indexed artifact targets get the same line/range behavior as the slower resolver path.

The LinkIndex fast path is location-aware now. I’m widening the pager-only budget matcher so bounded scans don’t truncate `:12-40` or `#L12C5-L40C2` halfway through.

The budget matcher is updated. I’m adding the validator contract now so future core builds must keep exposing the split binding and its schema-version probe.

I spotted a bad assertion in the new validator test while writing it: the schema probe should fail when the version function is missing. I’m correcting that before moving on.

The new test landed in the middle of an existing long schema test, so I’m moving it below that test instead of leaving the surrounding artifact-link assertions split.

I’m repairing the validator test structure now: the artifact-link schema variants stay together, and the link-location binding check becomes its own separate contract.

I checked downstream references; only the expected resolver call sites needed the new tuple shape. I’m tightening the copy helper’s type now, then I’ll add/adjust coverage.

I’m adding focused unit coverage before the larger corpus changes: one for the new Rust-backed split facade, and a few resolver/copy checks that prove locations are applied outside the path search grammar.

The resolver tests now verify ranges, GitHub columns, and diagnostics against the base path. I’m adding copy coverage so the copied path includes line and column only when there is a real file resolution.

I adjusted the directory copy case to use a path shape the Rust grammar intentionally treats as path-like. Next I’m extending scanner tests for ranges and GitHub-style fragments while keeping ACE’s original matcher unchanged.

That parametrized scanner test needs `pytest` imported; I’m adding the missing import now.

The scanner tests are extended. I’m adding a LinkIndex-backed resolver case now, so the ACE fast path proves it applies a range without falling back to the slower resolver.

The ACE fast-path test is in. I’m moving on to the rendered-link corpus, which is the broader contract check for labels, follow, copy, edit, and past-EOF behavior.

The corpus patch touches the fixture shape, expected occurrences, and context roots. I’m keeping it data-driven: add one long source file, one plan doc, one configured `designs:` doc, then declare every supported line-addressed form against those files.

The corpus file has slightly different ordering around the filtered context, so I’m splitting that patch too. No corpus changes landed from that failed attempt.

I’ve got the exact corpus layout now. I’m applying the fixture additions in smaller groups: constants/body first, then fixture paths/context, then expected rows.

The corpus declarations now include all line-addressed strings. I’m adding the actual fixture files and document-root context next.

The fixture files are created now, including a `designs:` document root. I’m threading that optional root through the helper that builds the artifact-ref context.

Now I’m declaring the expected corpus rows. File-path copies get absolute `:line[:column]`; typed artifact refs keep their durable ref text exactly as rendered by the scanner.

The corpus expectations now cover every requested form. I’m updating the module exports so the navigation tests can reuse the new constants cleanly.

I’m adding a resolver-level assertion over the rendered corpus: for each line-addressed occurrence, the resolved target now has the expected scroll line, range, edit line, and column before the UI clamps anything.

The corpus contract now checks resolver fields and the past-EOF information toast. I’m adding the Textual pilot test for pressing a rendered `plan:...:12-14` label and seeing the range rail/reading scroll in the real screen.

The corpus covers typed refs, but I also want narrow resolver tests for typed artifact refs: base-first resolution with a location, and the one allowed whole-ref retry when the split base fails.

The focused resolver tests are in. I’m doing a quick text scan for stale line-parser symbols and then I’ll build/install the new Rust binding into the venv so the tests can actually import it.

The stale parser scan is clean for the pager resolver; the remaining `_prompt_jump_target` regex is an explicit non-goal prompt-panel matcher. I’m rebuilding/installing the Rust extension from the ratcheted core checkout now.

`just install` installed the cached 0.34.24 wheel for the Python extension and is still compiling the companion Rust LSP bits from the same core checkout. I’ll wait for it to finish before running tests.

The install is still building Rust crates; no errors so far. After it exits I’ll verify the new binding is importable before running the targeted test set.

Still building quietly. I’m letting it continue; this is the heavier part of the local Rust install path.

The build reached the LSP crate, so it’s near the end. I’ll do one more wait and then start the Python checks.

Install completed cleanly. I’m checking the binding import and then I’ll run the targeted tests around artifact refs, pager resolution, scanning, copy, ACE fast path, and the rendered-link corpus.

The new binding is importable and returns the expected split. The targeted pytest run found a couple of failures in copy/corpus coverage; I’m waiting for the full failure output so I can fix the actual behavior rather than guess.

The failures are all useful and local: two copy tests have swapped expectations from my patch, the core scanner canonicalizes `#L3C2` to `#L3`, and the new pilot needs to wait for the immediate scroll to settle after navigation. I’m fixing those now.

The scanner canonicalizes artifact `#L3C2` targets to `#L3`, so the action path needs to preserve the visible line-location suffix before resolving/copying. I’m teaching the document target helpers to ask the Rust split grammar whether the visible artifact ref carries a location and prefer that location-preserving destination when it does.

I’m patching the document action-destination helper now; this keeps `#L3C2` available to the resolver even though the artifact-ref parser’s canonical render drops the column.

The action/ref helpers now preserve unquoted visible artifact locations. I’m fixing the two copy test fixtures whose expected path strings were swapped.

The copy fixtures are corrected. I’m rerunning the failing subset before changing the pilot scroll behavior, because the destination-preservation change may also affect the navigation path.

The copy and corpus contract failures are fixed; only the new pilot scroll assertion remains. I’m pulling the focused failure details now.

The range mark is set, but scroll stays at top in the real press path. I’m checking whether `_scroll_to_line_mark` is being called with the right row and whether the scroll command is being applied or overwritten.

The scroll command was firing before Textual had computed the new document’s `max_scroll_y` (it was 0 at call time, 22 after layout). I’m fixing the pager to reapply the line-mark scroll after the refresh that lays out the new body.

The pager now reapplies the mark scroll after layout, guarded so it only runs for the same landed document/mark. I’m rerunning the pilot test.

The pilot test passes with the layout-aware scroll fix. I’m rerunning the full targeted set to catch interactions.

The broader targeted run is through the resolver, copy, scanner, ACE fast path, and most corpus tests cleanly so far. Waiting on the remaining rendered navigation and validator files.

The full targeted set is green: 140 tests passed. I’m checking formatting/static issues next, then I’ll run the project-required verification path.

The main diff looks coherent, and the targeted tests are green. Since this turn changed tracked files, I’m reading the project’s required lint/test memory before final verification.

The verification note requires `just check`. I’m going to run the formatter first so any purely mechanical style fixes happen before the full check gate.

Formatter ran cleanly and reformatted one Python file. I’m running the required `just check` gate now; it includes whole-repo lint plus the scoped test lane.

`just check` is underway. Formatting and ruff have passed; it’s moving through the heavier lint gates now.

The check run is still active without new output. I’m letting it continue rather than interrupting the gate midstream.

Mypy passed. The remaining lint gates include feature flags, scripts, symvision, toobig, validation, and then the scoped tests.

Feature-flag and Python-script lint passed too. Still waiting on the later static gates and scoped tests.

The lint gates keep passing; symvision/toobig and validation are next, then the selected tests.

Symvision and toobig passed. This is a good sign; the run is into validation/scoped-test territory now.

No new output yet; `just check` is still running. I’ll keep it on the rails until it finishes.

Validation passed. The advisory core-floor probe reports the new split binding is ahead of the published `sase-core-rs` floor, which is expected for this ratchet phase and did not stop the check. Scoped tests are next.

The scoped test lane is still running silently. I’ll wait for its summary.

Still no scoped-test output; the command is active. I’m continuing to wait rather than starting another verification in parallel.

The scoped lane is taking a bit, likely because this diff touches shared pager/artifact-ref paths. Still running cleanly so far.

No new output yet; I’m giving the selected tests more time.

Still running. I’ll keep polling until the check exits; we need the final pass/fail state before closing the bead.

The test stage remains quiet but active. This sometimes happens with the silent runner around scoped pytest; I’ll keep waiting for the summary.

Still no summary; the command has not exited. I’m staying with it.

The scoped run is still active after several minutes. Since it’s the required gate, I’m continuing to wait rather than downgrading verification.

Still running. I’ll give it another interval and then, if needed, inspect from a separate status command only after this process returns control.

No output yet, but the session is alive. I’m continuing to wait for the gate to finish.

Still active. The silence is not ideal, but interrupting `just check` would lose the required verification, so I’m letting it complete.

This has been quiet long enough that I’m going to inspect the local process tree in another shell while leaving `just check` running, just to see which subprocess is active.

The process tree shows our `just check` is in `test-scoped` running pytest with xdist; other workspaces also have checks running, so the quiet stretch is likely host contention rather than a hang. I’ll continue waiting for our gate to finish.

Still active. The scoped pytest has been running for several minutes under load; I’m going to keep polling.

No output yet. I’m staying on the required check; nothing else is being changed while it runs.

Still running silently. I’ll continue to wait for the scoped pytest summary.

The gate is still active; I’m checking the process tree once more to make sure our pytest is making progress rather than disappearing under the silent wrapper.

Our pytest workers are still alive, with several in disk-wait and several running. That confirms the gate is working under contention, not gone. I’ll keep waiting.

Still active. I’ll keep polling until the required check returns.

No summary yet. The check has reached the slow part; I’m continuing to wait.

Still running under the silent wrapper. I won’t start any new edits until it finishes.

The scoped pytest process is still active. I’m going to keep waiting; this is the last blocking verification step before bead cleanup.

Still no output from the silent runner. I’ll keep polling.

The check is still alive and quiet. I’m continuing to wait for completion.

I’m picking up from the verification run rather than restarting the work. The core implementation and focused test suite are already in place; I’m checking the long `just check` session now so I can either fix anything it found or close the bead cleanly.

The previous PTY handle didn’t survive compaction, so I’m checking the process table and repo state directly. If the earlier check is gone or unverifiable, I’ll rerun the gate rather than hand-wave it.

No old verification process is still running, and the tree contains only the expected implementation/test edits. I’m rerunning `just check` now so the close note is based on a fresh, observable gate result in this workspace.

`just check` is through setup and formatting. I’ll keep polling it; the next interesting checkpoints are lint, SASE validation, and the scoped pytest run.

The fast lint layers are green so far. It’s now in the slower validation/test territory where failures are more likely to be meaningful.

Type checking passed. I’m letting the remaining project-specific checks run to completion so we don’t leave any stale epic-symbol or corpus issue hiding in the tall grass.

Feature-flag validation is green too. The gate is still running normally, so I’m continuing to wait it out rather than interrupting it.

The custom lint stack is still clean. Next up should be the terminology/symbol checks and then the heavier pytest scope.

Terminology checks passed. I’m watching for Symvision and the final scoped test summary now.

Symvision and size checks are green. The SASE validation phase is the remaining pre-test checkpoint; after that we’ll see whether the broader scoped tests agree with the focused suite.

SASE validation passed; the core-floor probe is reporting the expected unpublished-core advisory for the new link-location bindings, but the gate continued. It’s now at the scoped test stage.

The scoped tests are running silently, which is the expected mode for this check. I’ll give it more time and only dig in if it exits with a failure summary.

Still in the silent pytest section; no failure output yet. This repo’s scoped run can take a while under load, so I’m letting it finish rather than spawning overlapping test work.

No news is still decent news here: the scoped run hasn’t emitted a failure summary. I’m continuing to poll it until it exits.

The test phase is still alive and quiet. I’m staying on it; once it returns, the next steps are `epic-symbols`, bead close, and the SASE final declaration.

Still waiting on the same scoped pytest process. I’m keeping this single gate run as the source of truth so we don’t muddle the result with parallel checks.

It’s been quiet long enough that I’m checking the process tree in parallel, just to distinguish a legitimately slow scoped run from a stuck worker.

The process tree shows active xdist workers consuming CPU, so this is slow rather than stuck. I’m leaving it alone and continuing to poll the original gate.

The workers are still running silently; nothing actionable has surfaced yet. I’ll keep the cadence until the gate gives us a summary.

Still in scoped tests. The gate has not emitted failures, and the earlier process check showed useful CPU activity, so I’m giving it another interval.

The scoped suite is still running in the background, quiet as designed. I’m continuing to wait; once this returns we’ll have the full project gate result.

No output yet from the silent runner. I’m not seeing evidence of a dead process, so I’m staying patient and keeping the verification single-threaded.

Still waiting on the same run. At this point it’s just the cost of the large scoped suite; I’ll keep polling until it exits.

The verification run remains alive and silent. I’m keeping an eye on it; no code changes until it gives a verdict.

It’s been long enough for another health check. I’m checking just the local `just check` process tree this time, with narrow output, so I can see whether workers are still making progress.

The local pytest master and four workers are still active, with CPU/I/O activity. It’s not wedged; it’s just chewing through the broad scope, so I’m returning to normal polling.

The gate remains in progress with no failure output. I’m still holding off on close/final until this run gives a definite result.

Still quiet. This is the least glamorous part of the work, but it’s the bit that keeps the bead closure honest.

No test summary yet. I’m continuing to poll the same run; there’s still no indication that intervention would help.

The scoped suite is still running silently. I’ll keep this loop going until it either passes or gives me something concrete to fix.

Still no output from the silent runner. I’ve kept it single-threaded and undisturbed, which is the right move for this kind of gate.

No verdict yet. I’m staying with the run; once it returns we can move quickly through epic-symbol cleanup and closure.

I’m doing one more narrow process check to confirm the workers are still active and haven’t settled into a dead wait. If they’re still consuming CPU, I’ll keep polling.

The workers are still active, including one running and several in disk-wait while doing real work. I’m continuing the same gate run.

Still no failure summary; scoped tests continue. I’m waiting this out rather than replacing the run.

No output yet. The run is still alive; I’ll keep polling at the same interval.

The gate is still in the large silent section. I’m continuing to monitor; nothing has changed in the workspace while it runs.

Still waiting on the scoped pytest result. I’m keeping the close blocked on this one final signal.

Still in progress, still silent. I’ll keep the verification watch going.

No verdict yet. The best path is still to let the current gate finish cleanly.

`just check` finished and the local changes themselves made it through the broad run, but the gate failed on missing `continuation_decide_resume_adoption` from the installed core binding. That looks like the core pin I ratcheted for link-location support may need to include a later core commit that also contains the continuation binding, so I’m going to inspect the core repo through the SASE repo path before changing the pin.

I’ve reloaded the repo-opening rule so the core inspection stays audited. Next I’m locating the authorized core checkout and checking which commit contains both the link-location split and the continuation adoption binding.

The audited core checkout is available inside this workspace. I’m checking symbol presence and commit ancestry now; this should tell us whether to move the pin forward instead of holding it at the first link-location commit.

The currently opened core checkout is exactly the link-location commit and does not contain the continuation binding. The failing tests are therefore coherent: the repo’s Python side now expects a core commit beyond this checkout. I’m searching the primary tree and core history/remotes to find the correct pin.

I found the Python continuation facade already requires `continuation_decide_resume_adoption`, but the current core `master` checkout does not provide it. There is a release branch visible, so I’m checking whether it contains the missing binding or whether this is an existing upstream contract mismatch that the full-suite escalation exposed.

The release branch also lacks the continuation binding, and the current primary history shows the Python tests were expanded for resume adoption while the pinned core stayed at `ba651fe`. I’m checking whether the binding is only missing from `validate_sase_core_rs` bookkeeping or actually absent at runtime; the monitor failures suggest it’s runtime, but I want the exact source before deciding whether this is an out-of-scope upstream gap.

Runtime confirms the new link-location bindings are present and the continuation adoption binding is absent. I’m verifying that the previous core pin also lacked it; if so, this is a pre-existing full-suite failure exposed by `just check` escalation, not a regression from the link-location work.

The previous core pin lacked both the new link-location binding and the continuation adoption binding, so the continuation failures are not caused by my ratchet. One failure is likely mine, though: a core-contract validator test needs the new link-location schema included in its fixture. I’m fixing that before rerunning the focused verification.

Confirmed: the artifact-ref contract fixture missed `artifact_ref_link_location_wire_schema_version`, so that one is on my side. I’m adding it to the test fixture now; the monitor failures remain a separate missing-core-binding issue.

The contract fixture is updated. I’m rerunning the failing test plus the link-location focused suite, then I’ll format/check and record the unrelated continuation gap as a proposed follow-up on the bead.

The focused rerun is over halfway through and all green so far. I’m waiting for the final summary.

The focused suite is now clean: 141 passed. I’m formatting/checking the edited test file next, then I’ll add a bead note for the out-of-scope continuation core-binding skew that blocked full `just check`.

Formatting is clean. I’m recording the full-gate blocker on the current bead as a proposed follow-up now, per your instruction not to create a new bead myself.

The bead note command is taking a moment, likely on the bead store lock. I’m waiting for it to complete before doing any close checks.

The proposed follow-up note is on the bead. I’m running the required `epic-symbols` check now; if it’s clean, I’ll close only `sase-108.3`.

The status is still just the expected implementation and test edits. I’m waiting on the epic-symbols command, which is holding briefly on the bead store.

`epic-symbols` is clean: no leftover entries for this phase. I’m closing only `sase-108.3` with the verification note now.

The close command is submitted and appears to be waiting on the bead store for a moment. I’ll confirm it lands before doing the final SASE declaration.

The phase bead is closed. I’m doing the required SASE final declaration next; after that I’ll give you the concise wrap-up.

I’ve reloaded the finalizer instructions. Now I’m getting the host’s final context and will submit a commit declaration for the changed primary repo.

The final context requires one primary-repo commit declaration. I’m submitting it with `bead_action: "close"` because the assigned phase is complete and already closed.

The declaration submit rejected `bead_action: "close"` because the host couldn’t read the already-closed assigned bead status at submit time. I’m refreshing the final context and bead status, then I’ll resubmit with the action the host will accept.

The bead CLI doesn’t support `--json` on `show` here, so I’ll use the plain status output if needed. The final context refresh is still running.

The refreshed context is unchanged. Since the bead was closed explicitly before the finalizer, I’m resubmitting the commit declaration with `bead_action: "keep"` so the host commits the tree without trying to close an already-closed bead again.

Completed and closed `sase-108.3`.

Implemented the location-first line/column/range flow through the Rust-owned split grammar, pager resolution, file-path copy targets, ACE link index fast path, and the rendered-link corpus/pilot tests. I also ratcheted the core revision to the link-location binding commit and updated the core binding validator.

Verified:
- `just fmt` passed
- Focused link-location suite passed: `141 passed`
- `sase bead epic-symbols sase-108.3` was clean
- Full `just check` was run; after fixing my artifact-ref validator test issue, the remaining blocker is an out-of-scope missing core binding: `continuation_decide_resume_adoption`. I recorded that as a `PROPOSED FOLLOW-UP` on the bead.

Final declaration was accepted for the commit.
