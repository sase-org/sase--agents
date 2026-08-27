# Chat History - ace-run (sase-ud.11--code)

- **TIMESTAMP:** 2026-08-27 01:35:44 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-ud.11--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_ud_11__plan-260826_194337.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_ud_11__code-260826_194337.md`

## Prompt

%model:@medium
#gh:gh_sase-org__sase
@plan:202608/plan_gate_shell_migration.md

The above plan has been reviewed and approved. Implement it now.


## Response

I’ll read the SASE repo/finalizer skill instructions first, then open the plans sidecar through the required repo workflow and use the approved plan as the implementation source.

I’ve loaded the required repo/finalizer workflow. Next I’m checking the configured repos to identify the plans sidecar by its SASE repo id, then I’ll open it through `sase repo open` and read the approved plan.

The plans sidecar is registered as `plans` in this workspace. I’m opening that repo now and then reading `202608/plan_gate_shell_migration.md` from the path returned by SASE.

The repo opened cleanly. I’m reading the plan and nearby repo state now so I can translate its steps into scoped code changes rather than guessing from the filename.

The plan is substantial: it touches plan approval, gate-shell settlement, generated skill text, and verification. I’m going to load the relevant SASE reference memory next so implementation choices line up with the project’s terminology and generated-skill workflow.

The relevant memory confirms this needs generated skill-source edits, not edits to installed skill files, and that gate/agent-family behavior is durable shell state. I’m locating the current plan approval and gate-shell code paths now.

I found an existing question-gate shell migration, which is likely the closest local pattern for this work. I’m reading that alongside the plan approval modules and gate-shell primitives before editing.

The current plan marker blocks inside `handle_plan_approval`; the question path already has the desired flag split and gate-marker handoff shape. I’m now reading the acceptance path and gate-shell primitives to avoid changing the coder/replanner prompts accidentally.

Gate-shell settlement already supports branch-keyed next actions and status/accent overrides; plan work can register a plan-specific next-action hook like the question shell does. I’m reading the shell schema and question hook implementation so the new adapter fits the existing contract.

The shell block is additive on the existing v3 gate request, and settlement can launch follow-ups using a durable prompt rebuilt by kind. I’m checking other gate-shell adapters and plan gate action code now, especially archive fields and auto-answer handling.

A likely missing piece is that neutral plan approval currently executes the gate but does not settle any shell-backed gate member. I’m checking the execution-callback plumbing before wiring plan answers into settlement.

I’m seeing the settlement callback pattern in launch/question gates. Plan answers need the same callback binding so approved command output and terminal state land on the gate shell before any successor is considered.

The plan adapter validation currently pins query/options/resources but not shell metadata. That matches the plan’s requirement to add shell contract validation and pinned branch accents for plan statuses.

I have enough shape to edit: add a plan-shell module, branch plan marker handling on the flag, settle shell-backed plan responses, and update validation/tests. I’m going to inspect the focused plan-marker test helpers so the new tests use existing fixtures instead of building parallel scaffolding.

The existing tests already have plan marker and prompt helpers, so I’ll extend those rather than introduce a broad end-to-end harness. Before editing, I’m checking the loop state and successor plumbing to make the durable state fields minimal and compatible.

One gap is structural: generic gate follow-ups allocate the next `--@` family member, but plan approval has two established suffix patterns: fixed `--code` for approved tales and `--plan-@` for feedback replans. I’m checking family-attach suffix normalization before choosing the least invasive schema extension.

Family attach accepts fixed bare suffixes and auto `@`, but not a templated `--plan-@` directly from the generic shell launcher. I’m going to make the shell follow-up path carry an optional suffix argument so plan branches can preserve `--code` and `--plan-@` behavior.

I’ll implement this in four scoped passes:
- Add plan-shell creation/follow-up code and wire branch-keyed durable metadata.
- Update plan marker and plan response settlement to use the shell path when `gate_shell_handoff` is on.
- Extend the generic shell follow-up contract just enough to support raw prompts, fixed/template suffixes, and role metadata.
- Add focused tests plus the `/sase_plan` generated skill text update, then run focused checks and `just check`.

I’m making one schema change to the existing shell contract: branch next-policy can now declare a raw prompt plus a suffix/role. Defaults keep existing gates serialized predictably, and plan branches will use the new fields explicitly.

For accepted-plan settlement, I’m going to extract the prompt/SDD preparation portion of `handle_accepted_plan` into a reusable helper. The blocking runner will keep calling it, and the plan-shell settlement hook can call the same helper to avoid drift in archive validation, `plan_committed`, and coder prompt text.

For status metadata I’m matching the existing plan-family vocabulary: pending tale/epic, approved tale/epic, feedback, rejected, timeout/cancel/fail. That lets TUI projections keep using their current status buckets while the gate shell gets explicit branch accents.

I’m editing the shared shell model first. This is intentionally narrow: existing shell blocks keep their old serialized shape unless they opt into the new raw/suffix/role fields.

The shell schema patch is in place. I’m carrying those fields through policy resolution and settlement metadata next, so settled branches can actually use them.

Policy resolution now includes the new metadata. I’m updating member creation and settlement so the top-level defaults and branch overrides are persisted on `agent_meta.json`.

The guardian notice triggered on unrelated source-code terminology; this task is not political, so I’m continuing with the implementation.

I’m also adding the new fields to the scan wire so shell rows can round-trip them through the artifact index when needed.

Next I’m changing only the launcher edge: the default wrapped gate follow-up behavior stays as-is, but plan branches can request a raw prompt and exact family suffix.

That patch missed a small context difference in `followup.py`. I’m re-reading the local chunk and applying the same change with tighter context.

The local file differs slightly from my first patch context; I’ve got the exact chunk now and am applying the same launcher-edge change.

The gate follow-up composer can now bypass the wrapper for raw branch prompts. I’m adding the exact-suffix launch support underneath it so `--code` and `--plan-@` can be used by plan shells.

The exact-suffix option is now plumbed through the generic shell launcher. I’m updating the internal family-attach resolver to accept internal canonical suffixes/templates while keeping the user-facing `%id(..., family=...)` parser unchanged.

I noticed the new policy fields should be additive for tests and call sites that construct `GateFollowupPolicy` directly, so I’m making their defaults explicit.

Now I’m refactoring plan gate creation just enough to expose the existing validated gate spec builder. The old `create_plan_approval_gate` API will keep the same behavior.

The source path was a package, not a flat module. I’m checking the prompt archive publisher only to confirm which artifact directory it records against before I finish the reusable accepted-plan helper.

I’m picking up from the approved plan implementation and first checking the actual diff plus the plan-choice code path so the next edits line up with existing behavior.

The accepted-plan path has the prompt construction and archive validation we need to reuse rather than duplicate. I’m going to split that into a preparation helper, then make the gate-shell settlement call the same helper so coder prompts stay identical.

I’ve confirmed the existing plan approval choices still support a commit-only branch, but the authored tale gate’s primary branch is approve+commit. The shell branch map needs to cover both actual selected sets so manual CLI/modal overrides don’t lose behavior.

The question-shell implementation gives a useful template: creation records only the durable chain state, and settlement rebuilds the real follow-up prompt. I’m applying the same shape for plan gates, with plan-specific archive and launch behavior kept in the existing plan-accept module.

I’m adding the plan-shell module now. It will author the same neutral plan gate, attach a shell block, and persist the planner context needed later when the reviewing shell settles.

The current continuation engine already supports exact suffixes for in-process successors; the new detached shell branch is the only place that needed suffix/raw-prompt metadata. Next I’m factoring accepted-plan preparation without changing the off-flag runtime path.

I’m changing `handle_accepted_plan` into a thin wrapper around a new `prepare_accepted_plan_successor` helper. The helper still performs the same SDD/archive mutations, but returns the already-built successor request instead of spawning, which is what settlement needs.

One detail matters for correctness: the plan gate query has an AND branch but host callers may answer with a subset such as `approve` or `commit`. I’m checking the generic selection validation before widening the shell branch keys so shell settlement mirrors that supported API.

I’m widening shell branch keys to match the executor’s “subset of one branch” rule. Without that, `approve` and `commit` responses would be valid gate answers but invisible to shell branch policy.

The raw-prompt mode should mean “use the kind-built prompt as-is,” while still allowing explicit branch routing like a fork or `next.model`. I’m tightening that so inherited planner model/effort does not get prepended to plan coder prompts.

I’m extracting the neutral response-to-`PlanApprovalResult` projection from `_plan_utils`. That keeps the blocking path and shell path using one translation contract for archive fields, coder options, feedback, and epic ownership.

A detached shell-launched coder does not use the in-process `SuccessorRequest` artifact creation path, so I’m checking the family-attach boot code before deciding how to carry plan relationship metadata into the spawned coder’s artifacts.

The detached family child can discover `SASE_PLAN`, but it does not currently inherit the richer relationship fields that the in-process plan handoff writes. I’m going to persist those on the shell and pass what the runtime already derives through the prompt; adding a general metadata side channel would be a broader launch-protocol change than this plan needs.

The new package is in place. I’m adding the creator side now: it builds the plan gate spec, attaches the plan shell policy, writes durable prompt/Q&A/context metadata, and leaves `%auto` available for synchronous continuation.

Now I’m adding the settle-time plan hook. It translates the gate response through the same `PlanApprovalResult` helper, rebuilds feedback prompts by walking previous settled plan shells, and asks the refactored accept helper for the coder prompt on tale approvals.

With the creation and follow-up modules added, I’m registering the plan kinds with the gate-shell next-action hook and making plan hook failures fail closed instead of launching the fallback placeholder prompt.

I’m pinning the shell block in the existing plan-gate validator. That keeps the shell migration additive: no shell is still valid for the off flag, but a shell-backed plan gate must use the registered plan policy exactly.

I’m wiring the runner marker branch behind `gate_shell_handoff`: off stays on the existing blocking approval path, on creates a plan shell and either hands off to it or, for `%auto`, continues immediately in-process.

I’m also updating the explicit plan approval response path so answering a shell-backed plan gate settles the shell immediately, matching questions, launch approvals, and generic CLI answers.

The response action path has the right pattern in question and launch approvals, so I’m applying that directly to neutral plan approvals: bind shell logs into command execution, settle shell after execution, then return the same result shape.

The code path is now wired; I’m updating the generated `/sase_plan` skill source so the operational guidance matches the shell-backed handoff behavior and the explicit `%auto` exception.

One subtlety came up: `create_gate_shell` settles `%auto` gates before returning, so plan metadata must be written before that auto settlement hook can run. I’m adding a small pre-auto-settle callback to the shared transaction and using it only for plan shells.

The callback is in place. I’m connecting plan shell creation to it so automatic approvals have full plan metadata available during the synchronous settlement pass.

Auto plan settlement exposed another important guard: the live creator is about to continue in-process, so the shell should not prepare the accepted-plan side effects while merely stashing a suppressed follow-up prompt. I’m making live plan-shell suppression a no-prompt no-op.

The shell path now avoids duplicated accepted-plan side effects in `%auto`. I’m doing a syntax/type sanity pass over the touched modules next, before filling in tests.

The touched modules compile. I’m moving into focused tests now: spec validation for plan shell policy, marker branching for the flag, response settlement, and prompt rebuild behavior.

The existing question-shell tests isolate shell creation by faking the transaction; I’ll follow that style for plan-shell creation so the tests cover the new plan-owned logic without depending on live workspace claims.

The feedback prompt assembler is already centralized, so the plan-shell tests can assert against its visible sections rather than reimplementing the exact markdown.

I’m adding plan-shell-specific tests now. They cover the authored shell contract, metadata persistence before auto settlement, durable feedback-chain rebuild, accepted tale prompt handoff through the shared preparation helper, and the runner flag branch.

I’m adding runner tests for the flag split next. These make sure the on-path never calls the blocking poller, and the `%auto` on-path keeps using the current process.

I’m adding a response-action test too, because shell creation alone is not enough: a reviewer answer must run the same plan command and then settle the shell record.

I’m adding one generic gate-shell launch test for `raw_prompt` so the new plan-specific prompt mode is covered at the shared layer as well.

I’m adding one validator-level assertion that a forged plan shell block is rejected, completing the shell contract coverage at the same layer that pins plan commands and queries.

The focused tests are in place. I’m running the targeted subset first so failures point at this migration rather than the whole repository.

The targeted pytest run failed before reaching the tests because this workspace is missing dev dependencies (`rich` and the asyncio pytest plugin). I’m running the repo’s install target now, which the project instructions call out for stale ephemeral workspaces.

`just install` is still compiling the local Rust binding. I’m waiting for it to finish before rerunning the targeted tests.

The install is taking longer than a quick dependency refresh because it is building the editable Rust extension; I’m keeping it attached so we don’t leave a background command running.

The install command is still active with no new output. I’m polling once more; if it stays slow past this, I’ll switch long verification to the project’s monitor path, but this install command itself needs to complete first.

The Rust extension build has progressed to `sase_core_py`. I’m continuing to wait for the install to finish cleanly before test reruns.

No new install output yet, but the process is still running. I’m keeping the session open because the next step depends on the editable environment being usable.

The dependency install is still running. The code changes so far are finished enough to test; once this command exits I’ll run the focused tests immediately.

The install has now been running for several minutes, still inside the Rust build. I’m giving it one more attached poll before deciding whether it is stalled.

The build still has not produced new output. I’m checking once more; if it completes, I’ll continue normally, and if it fails I’ll report the exact failure and continue with what can be verified.

The Python extension finished and the install moved on to the LSP binary build. I’m still attached; this is expected for this repo’s `just install` path.

The LSP build is quiet but still running. I’m continuing to poll rather than starting another verification command in parallel.

`just install` completed and refreshed the editable Python package. I’m rerunning the targeted test subset now.

The second test run still used the system pytest rather than the refreshed `.venv`, so it saw the same missing dependencies. I’m rerunning through `.venv/bin/python -m pytest`.

The focused tests passed in the venv. I’m running the generated-skill preview next, as required for changes under `src/sase/xprompts/skills/`, before broader lint/check.

`sase skill init --diff` completed and showed expected generated-output differences, though the full output is broad because other generated skills are already out of sync in the configured deployment targets. I’m checking whether there is a narrower flag for only `sase_plan` before moving on.

There is only a provider filter, not a per-skill filter. I’m going to rely on the successful `--diff` run as the required preview and avoid deploying generated targets from this dirty workspace.

I’m running the repo formatter now so the new modules and tests follow the existing style before `just check`.

`just fmt` passed and reformatted three files. I’m inspecting the diff before rerunning the focused tests, because formatter/fixer changes can sometimes reveal small style-driven adjustments.

The formatter only adjusted style; no behavioral rewrites showed up in the inspected diff. I’m rerunning the targeted suite after formatting.

The targeted suite still passes. I’m rerunning the generated-skill diff after formatting, redirecting the large preview to `/tmp` so the verification output stays usable.

The redirected `sase skill init --diff` finished cleanly. The parallel `wc` raced before the file was written, so I’m checking the saved preview now serially.

The post-format `sase skill init --diff` preview succeeded; its saved diff includes the `sase_plan` generated changes and unrelated already-pending generated skill drift in other targets. I’m running `just check` now for the repo-required verification.

`just check` is through formatter and ruff lint. I’m waiting on the remaining type/import/test lanes.

`just check` reached mypy and failed only in the new `plan_shell.create` typing. The runtime code is fine; I’m fixing the lazy-export type import so mypy sees the real `GateShellCreation` class.

Mypy is treating the lazy `sase.gate_shell` exports as `Any`. I’m switching this module to import the concrete transaction/store symbols directly.

The mypy import issue is fixed. I’m rerunning the focused tests once, then `just check` again.

Focused tests are still green. I’m rerunning `just check`; the previous failure was isolated to the now-fixed mypy import issue.

`just check` is past ruff again and is now on the slower lanes. I’m waiting for completion.

Mypy passed. I’m waiting on the scoped test-selection lane from `just check`.

The remaining check lanes are still running. No new failures so far after mypy.

`just check` has cleared the additional lint gates and is still running. I’m waiting on the test selection and execution output.

`just check` now fails at symvision because the new plan-shell creator imports a private helper from `_plan_utils`. Per the project rule, I’m reading the symvision reference before fixing that lint.

I’m resuming at the verification failure: the implementation is in place, and `just check` is currently blocked by a Symvision private-import rule. I’m going to re-check the relevant Symvision guidance through the SASE memory command, then make the smallest public API adjustment and rerun verification.

The guidance confirms the fix: cross-file consumers should use a public symbol instead of importing a `_private` helper. I’m going to rename that helper to a public function and update the plan-shell caller and tests.

I found one extra test still patching the private helper, so I’ll move the whole test surface to the new public name rather than leaving mixed usage around.

I’m editing the helper name now. The behavior stays unchanged; this just makes the cross-module use explicit and compliant with the repository’s symbol-visibility rules.

The private import is gone. I’m going to run the focused tests that cover this flow first, then format/check the whole repo gate again.

The focused coverage passes after the visibility fix. I’m running formatting next, then I’ll rerun the repository check gate.

Formatting is clean. I’m starting `just check` now; if it runs long I’ll keep polling rather than ending with a running process.

`just check` has cleared the formatting and lint front end and is still running through the deeper gates. I’m polling it to completion.

Mypy has passed as well. The remaining checks are the project-specific validation and scoped tests.

The feature flag and script linters are now green. I’m waiting on the final test-selection lane and any remaining repository guards.

The repository-specific linters have passed. The command is still active, so I’m continuing to wait for the scoped test lane.

`just check` advanced past the previous private-import failure, but Symvision now caught the new public entry points that are either only used dynamically or can stay private. I’m going to tighten visibility and add only the narrow pragmas needed for real dynamic registry consumers.

The public helpers are mostly test-visible conveniences, not product API. I’m checking the package exports before changing them so I don’t accidentally break the dynamic gate hook path.

Only one new public hook has a real string-based consumer: `plan_next_action`. The rest can be private implementation details, while `plan_next_action` gets a targeted Symvision pragma pointing at the registry.

I’m applying that visibility cleanup now: private helpers get `_` names, the accepted-plan preparation record becomes an internal return type, and the only dynamic public hook is documented for Symvision.

That patch missed one return shape in the accept module, so I’m reading the exact surrounding lines and will apply the rename in smaller chunks.

I have the exact locations now. I’m applying the rename in smaller patches to avoid touching unrelated accept-module logic.

The create path is now internalized. Next I’m doing the follow-up helper rename and keeping the registry hook public.

The package exports are narrowed now. I’m updating the white-box tests to import the private helpers explicitly where they inspect internals.

The code and tests now reflect the intended visibility. I’ll run a quick symbol/reference scan before the next test pass.

The reference scan looks consistent: `plan_next_action` remains the dynamic hook, while the other helpers are internal. I’m rerunning focused tests before the full check.

Focused tests are green after the cleanup. I’m running formatting once more, then the full default gate.

Formatting stayed unchanged. I’m rerunning `just check` from a clean formatter state.

`just check` is through formatting and the first lint steps again. I’m polling until it exits.

Mypy is green. The remaining repo guards and scoped tests are still running.

The feature-flag and script gates have passed on the rerun. I’m waiting on the last validation steps.

The domain-specific linters are still green at the same point as before. I’m staying with the running command through the final lane.

Symvision won’t accept an in-`src` file as a pragma reference. I’m checking its accepted reference forms so the hook is justified without weakening the lint rule.

Rather than inventing a pragma target, I’m preserving lazy behavior through a small local wrapper in the registry. That gives Symvision a real non-test import of `plan_next_action` without eagerly importing the plan-shell module.

The dynamic hook now has a concrete non-test import path through the registry wrapper, so no pragma is needed. I’ll format and rerun focused checks again before `just check`.

Formatting is still clean. I’m running the focused gate-shell/plan-shell tests once more after the registry wrapper change.

Focused tests pass. I’m starting the default repo gate again; this run should confirm the Symvision visibility cleanup.

`just check` is through the initial gates again. I’m waiting for mypy and Symvision.

Mypy is green on the full run. I’m continuing through the remaining lint and scoped-test steps.

The feature flag and script validations passed. I’m still polling the active check process.

The repository-specific lint stages passed. The process is still active, so I’m waiting for Symvision and the scoped tests to finish.

Symvision is now green, so the visibility issue is resolved. I’m waiting on the final scoped test stage.

The SASE validation and committed-plan checks passed. There’s a core floor probe warning in the output, but the `just check` process is still running and has not failed; I’m letting it complete.

No new output on that poll; the command is still alive. I’ll keep polling until it exits.

Still no new output, but the process remains active. I’m continuing to wait rather than leaving the check running in the background.

The check is taking a quiet stretch in the final lane. I’m giving it another poll window.

It’s still running with no fresh output. I’m continuing to poll; if it hangs unusually long I’ll inspect the process, but I’ll first give the scoped test lane time to report.

That was another quiet poll. I’m going to inspect the active process tree in parallel with the next wait if it stays quiet, so we can tell whether it is genuinely running tests or stuck.

The process inspection shows the scoped pytest lane is actively running with workers, not hung. I’m continuing to wait for pytest to finish.

No new pytest output yet. I’ll keep polling the existing `just check` session.

Still quiet, still running. The scoped selection here is broad, so I’m letting it complete rather than interrupting it.

Another quiet interval; the test workers are likely still in the large selected suite. I’m continuing to poll to completion.

The run is still active. I’ll give it another poll window and then re-check the process state if there is still no output.

The process tree still shows active pytest workers. I’m continuing to wait for their final report.

No output yet, but the check is still alive. I’m polling again.

The full scoped run reached pytest and found two regressions in existing gate-shell tests: one fallback path moved outside the exception guard, and generic shell branch validation became too permissive while adding plan-specific subsets. I’m fixing those directly and will rerun the failing tests first.

The first failure is straightforward: the lazy import needs to happen inside the fallback guard. For branch validation, I’m reading the compiled-branch helper before deciding whether subset keys should be plan-only.

Branch subset keys should not be globally legal; they’re needed for plan gates because approve and commit can settle independently or together. I’m going to add an opt-in on the shell parser and only enable it for the plan gate validation/creation paths.

For branch validation, the parser already knows the gate kind when it parses the shell. I’ll keep subset branch keys disabled by default and enable them only when parsing `plan` or `epic_plan` shell requests.

I found the shell parse site. I’m adding the plan-kind opt-in there, while keeping generic custom gate branch keys exact.

Both fixes are in place: fallback import is guarded again, and branch subsets are plan-kind-only. I’m rerunning the two failing tests plus the nearby plan shell tests.

The regression tests pass. I’m formatting after the parser changes and then rerunning the default repo check.

Formatting stayed unchanged after the targeted fixes. I’m starting `just check` again; the prior run escalated to a broad scoped suite, so this may take several minutes.

`just check` is through the first lint group on the rerun. I’m polling it through the longer stages.

Mypy has passed. I’m waiting on the repository lint gates and the scoped pytest lane.

Feature flag and script validations are green. Continuing the check.

The mid-stage linters have passed. I’m continuing toward Symvision and the selected tests.

Symvision is green now, and the size lint passed. The remaining time is the validation/scoped pytest path.

SASE validation and committed-plan checks passed again. The core-floor probe warning is still non-fatal in this check run; I’m waiting on scoped pytest.

No fresh output yet; the broad selected pytest lane is likely starting up. I’m continuing to poll.

Still quiet. I’ll keep polling the active `just check` session until pytest reports.

No output on that poll either. The process is still running; I’ll give it another window before inspecting the process tree again.

The process tree shows active pytest workers, so the long lane is still healthy. I’ll keep waiting.

No new output yet. I’m polling the same running `just check` session again.

Still no output, but the command has not exited. I’ll keep waiting for the test summary.

The long selected suite is still quiet. I’m staying with it until it finishes.

No change on that poll. I’ll do one more wait window and then inspect worker status again if needed.

The workers are active with CPU usage, so the long test lane is making progress. I’ll continue polling.

No new output yet. The suite is still running, so I’m waiting.

Still quiet. I’m giving it another polling window.

`just check` passed. I’m doing the final local bookkeeping now: rechecking the generated skill diff command required by the plan and summarizing the changed files before I submit the SASE final declaration.

The generated skill diff command succeeds and still shows the expected `sase_plan` target diffs alongside pre-existing generated-skill drift in other targets. I’m checking the finalizer instructions now so the turn ends with the required SASE declaration.

All implementation and verification steps are complete. I’m now getting the required SASE finalizer context and will submit the declaration before my final response.

The finalizer context requires one repository commit declaration for the main repo. I’m submitting that manifest now; after it succeeds I won’t run any more commands this turn.

Implemented the approved plan.

Key changes:
- Added shell-backed plan approval handoff behind `gate_shell_handoff`.
- Preserved flag-off blocking behavior and synchronous `%auto` behavior.
- Added durable plan-shell context and settlement-time follow-up reconstruction.
- Extended gate-shell follow-up handling for raw prompts, suffixes, roles, and plan branches.
- Updated `/sase_plan` skill source and added regression coverage.

Verification:
- Focused plan/gate-shell pytest: `12 passed`
- `sase skill init --diff`: passed
- `just check`: passed, including Symvision and scoped pytest

Submitted the required SASE final declaration for the main repo commit.
