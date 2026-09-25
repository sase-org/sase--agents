# Chat History - ace-run (sase-110.4--code)

- **TIMESTAMP:** 2026-09-14 15:28:20 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-110.4--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202609/gh_sase_org__sase-ace_run-sase_110_4__plan-260914_113436.md`
- **2. --code** — `~/.sase/chats/202609/gh_sase_org__sase-ace_run-sase_110_4__code-260914_113436.md`

## Prompt

%model:@medium
#gh:gh_sase-org__sase
@plan:202609/ace_sudo_review.md

The above plan has been reviewed and approved. Implement it now.


## Response

I’ll open the sidecar through the SASE repo path first, then read the approved plan and let it drive the implementation. After code changes, I’ll run the project’s required verification rather than guessing at the right checks.

The repo inventory confirms `plans` is a sidecar for this SASE project. I’m going to open that audited path and read only the specific approved plan file next.

The sidecar opened cleanly and fast-forwarded, so I’m on the latest plan content for this workspace. I’ll inspect the plan and the current worktree state before touching files.

The plan is fairly broad: CLI answer contract, terminal handoff, ACE modal flow, typed gate labels, warnings, tests, and bead closure work. I’m going to pull the SASE reference notes that govern CLI changes, TUI responsiveness, beads, and verification before making edits, so the implementation fits the project’s guardrails.

I found the plan content. The first chunk of work is getting the constraints straight: CLI rules, TUI performance, bead lifecycle, and the mandatory verification note all apply here.

Now I’m mapping the existing sudo and gate paths. I’m especially looking for already-typed notification models and ACE modal conventions, because the safest implementation is likely to extend those rather than introducing a parallel flow.

There’s already a `src/sase/sudo` package and existing typed sudo gates, which is good news: the plan is an extension of a live path, not a blank slate. Because part of the work lives under ACE, I’m reading that local instruction file before editing those modules.

I’m going to read the existing sudo CLI/gate implementation and the ACE custom-gate dispatch/modal code side by side. That should reveal which pieces are missing versus already sketched.

I found the current approval path runs the whole manifest through `sase_sudo_runner` and then settles the gate. The approved plan’s biggest behavioral change is making approval bind to an explicit reviewed subset and returning retryable failures without settlement.

The ACE custom gate loader already follows the “off-pump, then modal” pattern from the performance note. I’ll mirror that shape for sudo review, then keep approval’s terminal handoff outside the durable gate-proc path as the plan requires.

The generic approval submission uses `_submit_durable_proc`, which the sudo approve path must bypass. I’m checking the notification dispatcher next so the sudo action can take precedence before generic `CustomGate`.

I’ve got the dispatch file now. The sudo handler will need to be exported alongside the existing notification handlers, then checked in the modal-flow switch before `CustomGate`.

The switch uses registry adapters, so sudo probably already has a typed gate adapter. I’m checking that adapter next because it controls whether ACE currently routes sudo through the generic form.

The executor itself already has a special preflight for sudo option inputs, so I’m reading that tail carefully before deciding whether the new subset binding belongs in generic executor code or the sudo CLI path.

The gate shell record already computes display status from its recorded start/stop pair, which matches the plan’s “data-driven” requirement. I’m tracing where that status is ignored or collapsed into generic labels.

`SUDO` and `SUDOED` are already being written into the gate shell metadata, but status bucketing still only treats `QUESTION` and `WAITING INPUT` as input pauses. I’ll come back to that after the approval path, since the label rendering may only need a small shared-status adjustment.

Status projection is shared between CLI/list integrations and the ACE models, and it already carries custom gate start/stop labels in several places. I’ll add specific tests around sudo labels as I wire the missing status surfaces.

The detail pane’s status-pair renderer is already generic; pending `SUDO` should appear once the loader puts the pair onto the row. I’m checking the phase-label helper because that is one of the few places that may hardcode `GATE`.

The status tests already cover custom pairs, so adding `SUDO`/`SUDOED` should be straightforward. The more delicate bit is the single active sudo-auth lease, so I’m looking for existing SASE-home locking and JSON durability helpers to reuse.

There are reusable gate durability helpers, including bounded flock support and atomic JSON writes. I’ll build the sudo auth lease on those primitives under `sase_home()/locks`, which keeps it host-wide and testable.

The subset binding needs to survive the final generic gate validation too, so I’m checking the approve command resource. If that resource only accepts a receipt today, I’ll update its schema and entrypoint to include the reviewed command IDs.

The modal can stay simple but still complete: a verified data projection, a selected-command set, a detail toggle, deny feedback, and a primary run button. I’m looking at local modal patterns for `Input`/buttons so it behaves like the rest of ACE.

For ACE loading, the notification carries bundle paths and typed action data, while the bundle carries the trusted sudo payload. I’m reading the notification model now so the modal can show requester/project/expiry without inventing fields.

The notification model has timestamps and action data, while the verified envelope has `created_at` and `gate_timeout_seconds`. That’s enough for an honest expiry line without adding another stored field.

I’ve got enough context to start editing. I’m going to add a shared sudo manifest/lease layer first, then thread it through the CLI, executor preflight, ACE modal/handler, custom-gate warning, and focused tests.

The lazy export table is the one place that needs modal registration. I’ll add the new modal there, plus its `.pyi` entries, so imports remain consistent with the existing ACE conventions.

I’ll keep subset manifest logic separate from both ACE and the CLI. That gives one enforcement point for default-all selection, unknown IDs, duplicates, original-order materialization, and the subset hash.

Next edit: new `sudo.manifest` and `sudo.lease` modules. The lease state will record request id, pid, host, user, run-as, cwd, command count, and timestamp only; no argv, hashes, transcripts, or credential-shaped material.

With the subset/lease layer in place, I’m updating the external runner call so authentication happens in the user’s terminal session while the JSON receipt stays machine-readable.

Now I’m threading selected command IDs through the approval input schema and command resource. That way the reviewed subset is checked before the gate decision is accepted and again by the bundle-owned approve command.

The gate schema now requires `command_ids` next to the receipt. I’m updating the approve entrypoint so it recomputes the exact subset hash from the immutable request before echoing an approval result.

The executor preflight is the other important guardrail. I’m changing it from “receipt matches whole manifest” to “receipt matches the reviewed command subset declared in option input.”

The CLI parser is next: `--run` becomes the explicit approve-and-run mode, and `--command` can be repeated to select reviewed commands. Omitting `--command` keeps the default-all behavior.

I’m moving the CLI approval path onto the reviewed subset: first choose command IDs, then compute the subset manifest/hash, acquire the auth lease, run the terminal runner, validate the subset receipt, and settle only on successful/command-failure receipts.

I noticed the top-level runner status check still only handled two retryable states. I’m expanding that to include cancellation spellings and timeouts so ACE can produce accurate retryable-error toasts.

For the sudo modal checklist, I’m going to use Textual’s `SelectionList`: it already gives stable toggle behavior, all-selected defaults, and keyboard selection without hand-rolling list focus mechanics.

There’s a local wrapping selection list for long question options, but it’s private to the question modal. For sudo command rows I’ll use ordinary `SelectionList` plus concise argv rows and a separate detail pane.

I’ll quickly check the installed Textual API for `SelectionList` construction so the modal tests don’t fight the widget.

The workspace’s bare `python` doesn’t have the editable environment active, so I’ll rely on the existing code and tests rather than probing the API globally. If verification shows the local venv is stale, I’ll run the required install step.

Actually, this clone has its own venv, so I’ll query that local interpreter for the widget signature.

The local Textual API confirms `SelectionList` supports `(label, value, selected)` rows and exposes `.selected`, so the sudo modal can stay nicely deterministic.

The style sheet already has a “gate review workbench” section. I’ll extend that section for `SudoRequestModal` rather than adding a whole new visual language.

I’m adding the dedicated sudo review modal now. It renders the verified request context, all-selected command checklist, detail toggle, feedback line, and explicit `Authenticate & run` primary action.

The modal file is in place. I’ll do a formatting pass later, but I already see one long helper line that Ruff will wrap; functionality first, then cleanup.

I’m extending the existing gate-review styles for the sudo modal and its command checklist, keeping it compact and readable in the same modal family.

I’ve got the approved plan and the partial implementation state in hand. I’m going to do a quick repo sanity pass now, then finish the ACE wiring, tests, and required verification.

The style patch did land, and the existing tree only shows the sudo-related files so far. Next I’m wiring the new modal into ACE’s notification path and keeping the terminal password prompt outside the Textual modal, which is the heart of this change.

The lazy modal package uses an explicit export table, so the new screen needs registration in three places. I’m also adding a sudo-specific handler beside the custom-gate handler so the privileged path stays typed instead of falling through to the generic form.

I found the generic durable executor: that’s exactly the thing sudo approval must bypass so the password never lands in a background task. I’m leaning on the existing `sase_argv` helper for the command shape but running it directly inside `suspend()`.

The custom gate modal already has the right shape for branch review, so I’m only adding a narrow warning field there. The sudo modal stays separate because it needs command selection and a terminal handoff, not arbitrary schema inputs.

The sudo gate already declares `SUDO` and `SUDOED` in its shell metadata, which is good. I’ll preserve that source of truth and update the few UI surfaces that were still hard-coding “GATE”.

The list row styling already honors whatever status label the loader gives it, including `SUDO` and `SUDOED`. The remaining status issue is mostly in prompt-panel headings, where the label was intentionally generic before typed gates existed.

I spotted one small logic leftover while reading: the interactive sudo prompt still returns the older string `"approve"` even though the new decision value is `"run"`. I’ll fix that while I’m in the file.

I’m going to make the sudo handler loader strict: it will only open when the verified bundle’s adapter and envelope both say `sudo`. That gives the modal trustworthy command data instead of relying on the notification row alone.

I’m at the edit point now. I’m going to add the typed handler, register the modal exports, add the password-warning field to generic custom gates, and tune the sudo status labels/CLI cleanup in one scoped patch set.

For the post-handoff refresh I’ll do the cheap cached refresh immediately and request the async agents refresh if the app exposes it. That matches the TUI performance rule: don’t force a full disk reconcile on the event loop.

Small correction before the patch: `GateShellRecord.status_bucket` is intentionally the coarse bucket (“Stopped”, “Done”), so I’ll compute a local status label for `sase sudo list` instead of changing the shared model.

The dispatch path is now explicit: `SudoRequest` gets the sudo modal before the generic gate fallback. Next I’m adding the custom-gate password warning so old/free-form gates visibly steer humans away from modal password entry.

The generic gate warning is in place with a fairly conservative detector: it requires a password word, a sudo/root/system target, and an ask/enter/provide-style verb in the same text chunk. Now I’m cleaning up the labels and CLI output.

The plain `python` on this machine isn’t in the project environment, so I’ll leave dependency introspection to `uv run`/`just` later. From local usage, Textual’s `SelectionList` toggles through its selection events, and I’ll tighten the event hook to that exact message type.

I checked the project environment for `SelectionList`; the toggle action exists, but the event name I used should match Textual’s actual `SelectionToggled` message. That’s a tiny polish patch now.

Now I’m moving into tests. I’ll start with focused unit paths: manifest subset binding, lease contention/release, sudo CLI non-terminal outcomes, ACE terminal handoff, modal command selection, and the custom password warning.

One important preflight tightening: if someone submits a valid receipt but omits `command_ids`, the gate must be rejected before the durable decision is accepted. I’m adding that now; otherwise the later schema failure would happen too late.

I’m adding tests in the existing sudo/custom-gate test files first so the new behavior sits beside the code paths it changes. After that I’ll add a small modal interaction test file for the new screen itself.

The sudo test file now covers subset hashing, pending-on-auth-failure JSON, and lease behavior. I’m adding one small projection test so the CLI list path proves it shows `SUDO`/`SUDOED` instead of the coarse buckets.

I’m adding ACE notification coverage next: sudo dispatch has to beat the generic gate fallback, and custom gates that smell like “enter root password here” should light up the warning field.

I’m adding a dedicated sudo notification test file now. It uses the real bundle loader but fakes the terminal command, so the coverage proves the argv, suspend wrapper, refresh, and “no durable proc for approve” contract without touching actual sudo.

A couple of the direct handoff tests need a dummy notification instead of relying on the store having one. I’m tightening that fixture now so the tests stay isolated.

Now I’m adding a compact modal test. It doesn’t need a full ACE app; just enough Textual host to mount the screen and verify default selection, details toggling, empty-run guard, and deny feedback.

I’ve got the notification/modal tests in place. One more status surface gets a focused assertion now: the prompt panel should still say `GATE` for ordinary gates, but `SUDO`/`SUDOED` for the typed sudo member.

I noticed I named one prompt-panel assertion “section” while still calling the phase renderer. I’m correcting that so it actually exercises the section heading too.

The status tests now cover both family phase and detail section headings. I’m going to add one render-level assertion for the exact custom-gate password warning string, since that text is security-sensitive.

I found an existing custom gate presentation test module, which is the right home for the exact warning text check. I’m adding it there instead of spinning up another one-off.

The helper that builds modal data accepts keyword overrides, so the render test for the password warning can be very small.

The security text now has a render-level test. The approved plan also asked for visual PNG coverage, so I’m going to add snapshot cases that use the existing visual harness; I’ll see whether the local golden-update flow is available after the functional tests are green.

I’m picking this up from the implementation state and going straight into verification/fixup mode: first I’ll inspect the diff and the visual snapshot harness, then I’ll run the focused tests and tighten anything that shakes loose.

The code footprint is where I’d expect for this feature: sudo domain helpers, CLI/executor changes, ACE modal dispatch, and focused tests. I’m checking the existing PNG snapshot style now so the new sudo review surface gets coverage that matches the local harness instead of inventing a parallel one.

The visual tests push modal screens inside the normal ACE shell and then compare committed PNGs, so I’m adding snapshots at that same layer. That should catch both the dedicated sudo modal layout and the generic-gate password warning without coupling tests to internal widget markup only.

I’m going to add two visual cases now: one for the new sudo review modal itself, and one for the custom gate warning state. After that I’ll regenerate just those goldens and let the focused test suite tell us where the edges are.

Visual cases are in place. I’m going to let the repo’s formatter normalize the new Python now, then I’ll run the sudo-focused tests before touching the broader check.

The repo has `just fmt`, so I’ll use that rather than guessing at individual formatter invocations.

Formatting completed cleanly. Next I’m running the focused sudo and modal tests first; that’s the fastest way to catch API mismatch before broad lint starts talking at full volume.

The focused suite is mostly green: 90 passed, with three small test-side mismatches. Two are a missing `json` import; the third is a Textual render object detail, so I’ll assert against the modal’s generated detail text instead of poking at a rendered visual wrapper.

I’m patching those test expectations now, keeping the production code untouched for this particular failure set.

Those failures are corrected. I’ll rerun Python formatting quickly, then the same focused suite.

Focused functional coverage is now green: 93 passed. I’m going to generate the new PNG goldens for the two added visual test files, then rerun those visual tests without update mode to make sure the committed images compare cleanly.

Pytest’s normal path deselects visual tests by default, so I’m checking the local visual recipe/options and will invoke it through the intended lane.

The visual lane has its own runner. I’ll rerun the three new visual assertions through `just test-visual`, first in update mode.

The first visual update produced two images and exposed a timing issue in the details snapshot: the modal was visible before its child widgets had mounted. I’ll wait for the child selector before toggling details so the snapshot setup mirrors a settled user-facing screen.

I’ll anchor the visual setup on visible modal text before toggling, then wait for the detail content after toggling. That removes the race without changing the actual modal behavior.

The race fix is in. I’m rerunning the visual update for the exact new cases.

The screen-text wait is too brittle here because the button label isn’t showing up in the exported text exactly as written. I’m switching to a selector-based readiness check against the modal widgets.

I found the local visual helper that polls semantic state directly. I’m using that for the sudo modal’s controls and then SVG text for the details sentinel.

That should make the visual setup deterministic under xdist. I’m rerunning the update pass again.

The new goldens are generated. I’m running the same visual cases in compare mode now.

Visual compare mode is green too. I’m checking a few neighboring gate loaders/executor tests next, since the approve schema and status labels changed underneath shared gate plumbing.

I included a stale visual test selector there; pytest rejected the whole command before running the useful neighbors. I’ll rerun the nonvisual gate plumbing checks cleanly.

The neighboring shared gate tests are green as well. I’m checking the diff shape now, then I’ll run the SASE symbol-scope check the plan calls for before the full `just check`.

The three new PNG goldens are untracked as expected. I’m running the plan’s epic symbol check now, which is the project’s guard against accidentally broadening this phase beyond its declared surface.

The epic-symbol check completed cleanly with no declared symbol scope entries for this bead. I made one small visual-test edit after the last formatter pass, so I’m formatting Python once more before the full check.

Everything focused is clean, so I’m starting the required `just check` now. This is the broad repo gate, so it may take a bit; I’ll keep an eye on it and fix anything it uncovers.

`just check` is through formatting, keep-sorted, and ruff. It’s still running the deeper checks now.

The full check found two type issues, both narrow: a TYPE_CHECKING import omission and Textual’s `SelectionList.action_toggle` name colliding with a base DOM action in mypy’s view. I’ll patch those directly.

Textual’s public method for the highlighted selection is `action_select()`, while `action_toggle()` belongs to the DOM base class in this version. I’m switching the modal binding to that public SelectionList action.

The type fixes are in. I’ll format and rerun `just check` from the top; after a failure it’s cleaner to let the whole required gate speak again.

Formatting is still clean. Restarting `just check` now.

`just check` is past the same early gates again. Waiting on mypy and the project-specific linters now.

Mypy is green now. The check is continuing through the custom SASE lint/test steps.

Feature flag lint is green too. Still waiting on the remaining project linters and tests.

The check has now cleared pyscripts, test-waits, and changelog lint. Symvision and the remaining suite are still running.

Terminology lint passed. I’m letting the longer symbol and test stages finish.

Symvision caught a few helper exports that don’t need to be public. I’ll make the internal path/id helpers private and keep only the externally used sudo review helpers exported.

The search confirms these are only used internally or by tests. I’ll rename the detection helper private as well and point the tests at the private helper, since it’s deliberately not a module API.

One import block had been formatted slightly differently than I expected, so that patch didn’t apply. I’ll split it into smaller edits against the exact current text.

I have the exact current blocks now. Applying the private-helper cleanup in smaller patches.

The manifest helper is private now. Next I’m doing the lease path helpers and the custom gate warning detector.

Private-helper cleanup is applied. I’ll format and run the focused suite once more before restarting the full check.

No stale public names remain, and formatting is clean. I’m rerunning the focused functional suite after the renames.

Focused tests remain green. I’m restarting `just check` again; this time the earlier symvision findings should be gone.

`just check` has cleared the early lint gates again. Waiting on type and symbol checks.

Mypy is green. The remaining custom linters and tests are still moving.

Feature flag lint passed. I’m still monitoring the broad check.

The project-specific lint stack is nearly through; symvision is next/ongoing, followed by toobig and the default test lane.

Symvision and toobig are green now. `just check` is in the default pytest lane.

No new output yet; the default test lane is still running.

SASE validation and committed-plan validation passed. The remaining test process is still active.

Still no fresh output; I’m giving the test lane a little more room.

The broad tests are still running silently. I’m waiting for completion rather than interrupting a healthy check.

Still in the long pytest stretch. Nothing has failed yet; just quiet output.

The check is still active. I’m polling again; these long quiet intervals are common in the default lane here.

Still running, still no failure output. I’m continuing to wait it out.

The default lane is taking a while but remains alive. I’ll give it another interval before deciding whether to inspect stuck workers.

Still quiet. I’m doing one more normal poll; if it stays silent much longer, I’ll inspect the live process tree in parallel without killing anything.

The check has been silent for several minutes, so I’m going to inspect the process tree while leaving it running. This is just to see whether pytest workers are still active or whether something has wedged.

That process-group probe was keyed off the tool session id, not a PID, so it wasn’t useful. I’ll inspect by command name instead.

The process list shows our `test-scoped` pytest lane is active in this workspace, alongside other workspace runs. I’ll keep waiting; it hasn’t wedged.

The scoped pytest lane is still running. I’m continuing to monitor it to completion.

Still quiet but active. Another poll.

The suite is still in its long no-output stretch. I’m letting it run; no signal yet that it’s failed.

Still active. I’ll keep polling rather than restarting and losing the current run.

`just check` made it all the way through the full test lane and found three expected integration drifts: completion snapshot needs regeneration after sudo parser changes, and one new visual fixture used a host-home-looking path. I’ll fix those and rerun the failing tests plus the broad check.

The host-path test pinpointed the visual fixture: I used my local-looking home path in the new sudo modal sample. I’m changing that to the project’s allowed synthetic `/home/visual` path and then regenerating the affected sudo PNGs.

The fixture path is synthetic now. I’m regenerating just the sudo request PNGs, then I’ll refresh the CLI completion snapshot.

The sudo goldens are updated with the synthetic path. I’m regenerating the checked-in completion spec for the new `sase sudo answer --run/--command` surface.

Completion spec has been refreshed. I’ll rerun the three previously failing tests plus visual compare for the affected new snapshots.

The previously failing tests are green. I’m running the three new visual snapshots in compare mode one more time after the path change.

Visual compare is green again. I’m starting `just check` for the final required pass now; the previous full run only failed on the three drifts that are fixed.

The final `just check` pass is already through mypy. Waiting on the remaining lint and test stages.

Feature flag lint is green. Continuing through the custom lint stack.

Pyscripts lint passed. More lint/test stages are still underway.

Test-wait, changelog, and terminology lint are green. Waiting on symvision/toobig and the test lane.

Symvision and toobig are green on the final pass. The remaining time is the default test selection, which may be full-suite again because of generated completion identity changes.

SASE validation and committed-plan validation passed on the final run. Now it’s in pytest.

The pytest lane is active and quiet; continuing to wait.

Still running without output. No intervention yet.

The broad test lane is still in progress. I’m letting it finish.

Still quiet but alive. Continuing the wait.

No output yet from pytest. The previous run took several minutes at this stage, so this is still within the expected shape.

Still waiting on pytest completion.

The test process is still running silently. I’ll poll again.

Still no output. I’m going to keep it running; interrupting here would waste the near-complete broad pass.

The final check is still in the long pytest section. I’m continuing to wait it out.

Still active, still quiet. Another poll.

No fresh output yet from the final check. I’m waiting.

Still in progress. The broad run is expensive, but it’s the required gate for this repo.

The pytest lane is still alive with no output. I’ll keep polling until it returns.

Still quiet. Waiting another interval.

The final test pass is still not done. It should surface a summary when pytest exits; I’m staying with it.

Still running. I’m polling again.

No output yet. I’m leaving it alone and continuing to wait.

The final check is still active after another interval. I’m going to let it finish rather than risk a partial verification.

It’s been quiet long enough that I’m checking the active pytest processes again, just to confirm it’s still doing work.

The final run is active in `test-scoped` with a large but not full 41k-item selection, using 4 workers this time. Still healthy; continuing.

Still running. I’ll wait another interval.

No output yet. Continuing to monitor the scoped tests.

Still active and quiet. I’m staying with it.

No new output. Another poll.

The scoped test run is still in progress. I’ll keep waiting for the final summary.

Still quiet. Continuing.

The final check remains active. I’m polling again.

Still running with no failure output. Waiting.

No fresh output yet. Continuing to wait.

Still alive; still quiet. Another poll.

The final check is still in the long pytest section. I’m staying on it.

The final `just check` pass is green. I’m doing a last status/diff check now, then I’ll close the phase bead as requested by the approved plan.

The diff includes the regenerated completion spec and three new PNG goldens, which matches the work. I’m closing only the approved phase bead now, per the plan.

The phase bead is closed with a note. I’m checking status one more time to see whether the bead close touched tracked files before I wrap up.

The bead close only touched ignored SASE state; tracked status is just the implementation diff. I’m grabbing a few line anchors for the summary now, then the finalizer declaration is the last tool action before I respond.

I have enough to summarize the implementation and verification. I’m reading the SASE finalizer skill now and will make the required final declaration as the last tool action.

Using `sase_final` now: I’m fetching the host final context and then I’ll submit the commit declaration.

The finalizer context requires a commit declaration for the main repo, with `bead_action: "close"` because the assigned phase is complete and verified. Submitting that now; this will be my last tool action if it succeeds.

The finalizer rejected `bead_action: "close"` because it couldn’t read the assigned bead status, even though the explicit bead close command succeeded. I’m going to inspect the bead status and refresh the final context, then submit the manifest in the form the host can accept.

The bead status is visibly closed, but the commit finalizer’s own close hook cannot read that status and refuses the `close` action. Since the bead has already been explicitly closed and noted, I’m submitting the repository commit declaration with `bead_action: "keep"` so the host commits the verified work without trying to close it a second time.

Implemented the approved ACE sudo review plan.

Highlights:
- Added the dedicated `SudoRequestModal` and ACE dispatch/handoff path.
- Added reviewed command subset hashing, receipt validation, JSON pending outcomes, and a single-active sudo auth lease.
- Updated `sase sudo answer` with `--run` / repeated `--command`.
- Added `SUDO` / `SUDOED` labeling for sudo gate surfaces.
- Added the generic custom-gate warning: `Never enter your system password here`.
- Added functional, widget, and PNG visual coverage, plus refreshed CLI completion snapshot.

Verification passed:
- Focused sudo/modal suite: `93 passed`
- Neighboring gate plumbing suite: `85 passed`
- New visual snapshots: `3 passed`
- Required `just check`: passed
- `sase bead epic-symbols sase-110.4`: passed with no entries

Closed `sase-110.4` with an implementation note, and the SASE final commit declaration was accepted.
