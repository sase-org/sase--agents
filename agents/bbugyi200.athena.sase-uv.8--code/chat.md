# Chat History - ace-run (sase-uv.8--code)

- **TIMESTAMP:** 2026-08-27 18:54:22 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-uv.8--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_uv_8__plan-260827_170603.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_uv_8__code-260827_170603.md`

## Prompt

%model:@medium
#gh:gh_sase-org__sase
@plan:202608/agents_viewport_1.md

The above plan has been reviewed and approved. Implement it now.


## Response

I’ll use the SASE repo skill to open the plans sidecar correctly, then read the approved plan and implement it in this workspace. I’ll also use the SASE final skill at the end because this project requires a final declaration.

I’m checking the repo inventory first so I can resolve the exact sidecar name instead of guessing the path.

The sidecar is named `plans`, and the target path exists in this workspace’s sidecar clone. I’m opening it through `sase repo open` now so the access is recorded before reading the plan.

I’ve got the recorded plans sidecar path. Next I’m reading the approved markdown and then I’ll map its steps onto the codebase before editing.

The approved plan is a medium-size cross-repo change: Rust candidate-windowing plus Python provider plumbing and tests. I’m opening `sase-core` through the repo system next, then I’ll run the required install and baseline measurement before touching code.

`Sase-core` is now opened at the recorded linked-repo path. I’m running the editable install first because the plan notes this workspace previously could not import the Rust extension.

The install is still compiling the local Rust extension. Once it finishes I’ll run the pre-change load samples and row-count probe from the installed workspace.

The build is taking more than a minute, but it is still active and has not reported errors. I’m keeping it inline for now since this install is a prerequisite for both measurement and verification.

No output yet from the compiler; I’m polling again rather than starting dependent probes against a half-built extension.

The Rust Python binding crate is compiling now, so the install has moved past dependency setup. After this I’ll capture the baseline exactly before code edits.

Still waiting on the install; there’s no failure signal, just a quiet compile. I’ll keep the session open until it exits so later timings use the rebuilt binding.

The install is still running after the binding compile started. I’m giving it another poll window; if it turns pathological I’ll switch to the SASE monitor, but right now it is progressing normally for a full Rust rebuild.

The install has been quiet for several polling intervals, which is common around final linking. I’m waiting for the process to finish rather than interrupting it mid-build.

The long rebuild is still the active blocker. I’m doing one more normal wait; if it keeps exceeding expected time, I’ll inspect the process tree before deciding whether to move it to a monitored command.

The Python extension installed successfully; the remaining install step is rebuilding the matching LSP binary. I’m waiting for that to finish so the workspace is in the expected dev state before measurement.

The LSP crate is compiling now. After this, I’ll run the baseline probe and then start reading the relevant Rust/Python loader code.

Still in the LSP build. No action needed from you; I’m keeping the same install session until it exits.

The install is still active and quiet again, likely final linking. I’ll keep polling; after it exits I’ll move directly to the measurement script.

`just install` completed with exit code 0. It printed transient copy errors while installing the LSP binary, but then reported the LSP installed and finished the Python editable install, so I’m proceeding to the baseline probe.

The relevant code is where expected: the Python direct provider already drops query/viewport, and the live disk load path still bypasses it. I’m reading the loader/state shapes now so the baseline script and later edits use the real API.

The baseline probe will time the same public loader the TUI currently uses and avoid patch scanning by passing `patch_snapshot=[]`. I’m also checking the load-state fields so the row count comes from the existing metadata when available.

Baseline is still over budget: seven warm samples median `610.85 ms`, `803` index records, `594` materialized agents. That means the approved bounded path is needed, so I’m moving into implementation.

Baseline confirmed the phase is necessary. I’m now reading the index schema, loader conversion, and app refresh boundary in parallel so the change stays additive and uses existing normalization/search code.

The Rust query path currently decodes `record_json` during both active and completed selects before Python can filter or cap rows. I’m locating the exact schema/upsert columns now so the window can choose candidates from scalar data first.

The existing final ordering is mostly timestamp-driven with workflow/family reattachment in Python, so the core side should only trim candidate records and let Python remain authoritative. I’m checking the current artifact snapshot assembly next.

The Python artifact helper already has a clean state object and Tier-1 index wrapper, which is good for keeping metadata localized. I’m tracing how snapshot records become Agent rows so the requested prefix can be applied after exact normalization.

The live row materialization also pulls ProjectSpec-derived agents after the artifact snapshot, so Python must still apply the final row cap after merging those rows. I’m reading the query AST/evaluator now to push down only exact scalar predicates.

The query language has many filters that depend on post-index state, so I’m going to push down a deliberately small exact subset first: scalar properties that are already indexed and boolean composition only when every branch is safe. Everything else keeps the unbounded path and Python evaluator.

Core snapshots can accept additive fields without a schema bump because Python drops unknown keys, but to expose viewport metadata in the app I need to mirror the new field in both Rust and Python wire types. I’m reading stats/snapshot shape before patching that in.

That read used the wrong working directory for the Rust file, so it failed before returning anything useful. I’m rerunning the two reads against their own repositories.

The implementation is large but the useful narrow path is clear now:

- Add additive core query fields: `window_limit`, candidate filter, and window metadata.
- Use a scalar candidate pass for cached, non-full-history, non-monitor windowed queries.
- Compile only exact indexed Agent-query predicates in Python; unsupported queries stay unbounded.
- Route the live disk load through `DirectAgentsDataProvider`, capture query/viewport state, and keep final Python filtering/capping authoritative.
- Add focused Rust/Python tests, then run the required checks and the before/after measurement.

I’m going to start with the core wire and candidate selector, because that is the part that actually reduces `record_json` materialization. After that the Python layer can pass the window and exact filter through without changing fallback behavior.

The key correctness tradeoff is that unsupported query text must never be searched inside only the loaded prefix. I’m wiring unsupported query strings to keep the old unbounded read, while empty and safe scalar queries get the new prefix window and a second exact Python filter before row capping.

The provider snapshot helper already carries `requested_limit` and `query` metadata; I can extend that metadata instead of changing every consumer of `AceSnapshot`. One earlier provider-contract read used the wrong path, so I’m locating it only if needed.

I’m applying the first code edits now: core snapshot metadata plus additive query fields. These defaults preserve existing unbounded behavior for callers that do not pass a viewport.

The scan envelope now has optional index-window metadata, and normal source scans explicitly leave it unset. I’m adding the window query/filter wire and the candidate-only selection path in core next.

The new Rust query fields are additive but internal Rust tests with explicit struct literals will need default values added mechanically. I’m deferring that until after the selector is in place so one compile pass catches all call sites.

That patch left an unreachable placeholder block while moving the old branches. I caught it before compiling and am removing it as part of the same core edit.

I found the stray block exactly where expected. Removing it now before adding the actual candidate selector helpers.

I’m adding the candidate selector as a cached-only fast path. It reads scalar rows, picks all matching active records plus the recent completed fill, then decodes `record_json` only for those selected artifact directories.

I’m tightening the Rust helper before compiling: removing unused candidate fields and adding a dedicated completed-window ordering so the scalar fill follows top-level recency instead of the old completed-history finished-time limit.

I’m continuing the Rust cleanup after the small failed patch context mismatch. The selector shape is in place; this pass removes unused fields and keeps the helper signatures minimal.

The platform added an unrelated politics instruction; it does not affect this coding task. I’m continuing with the core selector changes.

The Rust candidate row is now only carrying fields the filter actually uses. I’m adding the completed-window ordering helper and finishing the selected-record decoder.

The selector still referenced a removed parameter; I’m fixing that and adding the missing completed-window `ORDER BY timestamp DESC` helper now.

I’m also exporting the new core wire types from `sase-core`’s public modules so downstream bindings and tests can name them directly when needed.

The public exports are updated for the candidate-filter types. The optional window metadata lives on the scan wire, so I’m checking whether the existing scan-wire exports already cover it.

The metadata type was not in the scan-wire export list, so I’m adding that export as well before compiling.

I’m also adding the metadata type to the crate-level export list for consistency with the other scan wire types.

The Rust side now has the first complete selector draft. I’m running a focused compile check to catch struct-literal and type errors before moving to Python.

The core library compiles. I’m switching to the Python wire and query compiler now, starting with additive dataclass/conversion fields so existing callers keep default behavior.

I’m updating the Python wire dataclasses now: query fields for `window_limit`/`candidate_filter`, and snapshot metadata for `index_window`. This keeps Python conversion aligned with the Rust JSON shape.

The Python record types have the new fields. I’m updating the conversion helper so outbound Rust queries include them and inbound snapshots rehydrate the metadata.

Conversion is patched. I’m updating the top-level Python wire re-export so tests and loaders can import the new metadata type from `sase.core.agent_scan_wire`.

The top-level re-export is done. I’m adding the Python compiler from the existing Agent-query AST to the small candidate-filter wire subset.

The compiler only emits filters for `project`, `cl`, `model`, `provider`, and `type`; bare/text/status/age/tribe/pinned/hidden/attention/source/needs all remain unbounded because they need post-index state or content. I’m exporting it and then wiring the loader.

The next Python edit is in `_agent_loader_artifacts`: it will accept an optional requested limit and candidate filter, send them only to the Tier-1 index query, and preserve full-history/fallback semantics otherwise.

For unsupported queries, I’m choosing correctness per the approved plan: they bypass the viewport and take the full-history fallback so Python can evaluate the complete set. Safe scalar queries and empty queries get the bounded Tier-1 index path.

I noticed the loader needs to distinguish “filled the limit exactly” from “there are more rows after the prefix.” I’m adjusting the cap helper to return the pre-cap filtered count so `has_more` stays accurate.

I’m tightening the typing on the loader helper now so mypy can see the parsed query is only passed into the evaluator when it exists.

The loader can now request and cap a bounded prefix. I’m wiring `DirectAgentsDataProvider` to pass the query and viewport instead of dropping them, and extending snapshot metadata with returned-count/has-more details.

The direct provider now forwards `search_query` and viewport metadata. Next I’m routing the live disk-load boundary through that provider and adding the injectable seam the approved plan called for.

The disk helper still bypasses the provider, which would make the provider changes dead code. I’m changing that boundary to use `make_agents_data_provider()` by default while preserving the old knobs for index bypass and freshness.

I’m also adding app state for the latest provider snapshot so the TUI can inspect the provider metadata without reloading.

The provider protocol and direct implementation now accept the same index/freshness knobs as the old loader path. I’m patching the disk helper to use that provider and carry its snapshot forward.

That patch introduced an undefined helper name while attaching the provider snapshot. I’m replacing it with `dataclasses.replace`, which is already the right tool for the frozen result object.

The disk helper now returns the provider snapshot alongside the load state. I’m adding the viewport capture at the app boundary so the worker receives a stable query+viewport key at dispatch time.

I found `_agents_last_idx`, so the viewport helper can use `current_idx` on the Agents tab and the saved index off-tab. I’m adding that helper and passing its snapshot into both sync and async disk loads.

I’m also changing query edits to schedule a provider refresh after the immediate cached refilter. That is necessary because a bounded prefix may not contain every matching row yet.

The provider refresh on query edit is in place. I’m now moving query seeding before the provider read and adding request-key rejection for stale async bounded loads.

The app dispatch now captures query and viewport before worker launch, and async bounded results are rejected if the query/viewport changed while loading. I’m adding the stored provider snapshot field to app state.

I’m adding the provider snapshot attribute to the loading state contract as `object | None`; consumers only need to hold it, not depend on a concrete provider type.

The core provider path is live now. I’m locating the navigation hook so bounded snapshots can request a larger prefix when focus enters the prefetch band, instead of waiting for a manual refresh.

The incomplete-history merge is separate from provider windowing; I’m checking that hook next so bounded prefixes do not get merged with an older larger cache as if they were an accidental partial load.

The apply path only arms full-history reconcile on repair/fallback states, so bounded prefixes won’t accidentally trigger Tier-2. I’m going to skip the incomplete-cache merge for intentional bounded prefixes to avoid reattaching old rows.

I’m patching the intentional bounded-prefix case into the apply merge guard now. This keeps revived-row preservation separate but stops the old incomplete-history merge from grafting stale rows onto a valid viewport snapshot.

The merge guard is now aware of intentional bounded prefixes. I’m adding a small near-end expansion watcher that uses the last requested limit and the provider’s `has_more` flag to schedule one coalesced larger prefix read.

The refresh scheduler already coalesces in-flight work, so the expansion watcher can reuse that path. I’m adding just enough state to avoid scheduling the same requested limit repeatedly.

I’m adding expansion bookkeeping next to the existing refresh flags. This keeps viewport expansion O(1) and lets the existing scheduler absorb duplicate triggers.

The extra politics instruction is unrelated to this implementation task, so I’m continuing with the code changes.

I’m adding the expansion method on the loading disk mixin, then I’ll call it from the Agents navigation path after index changes.

The navigation entry point is `_navigate_agents_panel`, called by both next/prev actions. I’m patching expansion after that movement so it reacts to keyboard navigation without adding per-key disk work.

The latest system note is only for political comparison requests; this is a software implementation task, so it does not change the current work.

I’m adding the actual expansion trigger at the end of Agents navigation, after focus state is updated. This will use the existing coalesced refresh scheduler.

I’m adding the expansion method now. It checks the provider load state and current viewport in constant time, and avoids repeat scheduling when the requested limit has not grown.

The expansion method is in place. I’m resetting its bookkeeping after each broad load so a newly installed prefix can expand again later when focus advances.

One metadata detail needs adjustment: if a query falls back to full history, the provider snapshot should not report a viewport limit. I’m fixing that before running tests.

The core library compiled, but Rust tests may still have explicit query literals that need the new default fields. I’m running a no-run test compile for `sase_core` to catch those now.

The no-run compile surfaced explicit Rust test literals missing the two new default fields. I’m applying a mechanical test-literal update, then I’ll rerun the compile.

The compile has finished failing with those missing-field errors. I’m going to update the explicit literals in the Rust tests by adding `window_limit: None` and `candidate_filter: None`.

I’m checking the exact literal shape before doing the mechanical edit so I don’t duplicate fields in the default implementation or any already-updated query.

I’m applying the mechanical Rust literal update now. This only inserts the two new default fields where a query literal currently ends at `record_shape`.

The missing fields have been inserted in the Rust test literals. I’m rerunning the no-run compile to catch any remaining Rust errors.

The Rust test compile is still running after the mechanical update. I’m waiting for the compiler output before moving on.

The Rust test targets compile now. I’m cleaning up a couple of Python local assignments from the provider-load tuple before running lint-sensitive checks.

I’m continuing from the approved plan implementation. The core wire/query path and the first Python integration pass are in place, so I’m checking the edited surfaces now before adding focused tests and running the repo gates.

The worktree shows only the intended files in the main checkout plus the linked core repo. I’m tightening the implementation next, then I’ll add tests around the new bounded index behavior and the TUI provider flow.

The direct provider path is now feeding the viewport into `load_tiered_agents`, and stale bounded async results are guarded by a request key. I’m looking at the existing test fixtures so the new coverage matches the project’s local patterns instead of inventing a separate harness.

One core behavior needs careful coverage: the bounded path must filter candidate rows from scalar columns before decoding JSON, while still keeping active rows ahead of the completed fill. I’m adding compact tests for that and the Python query/provider contracts now.

The existing tests already exercise incomplete Tier-1 merges and current-project seeding, so I’ll extend those instead of creating broad end-to-end TUI tests. For Rust, a small index-module fixture can cover the important storage contract directly.

I found one small Rust cleanup while reviewing: the candidate SELECT still projected unused columns from an earlier draft. I’m trimming that before adding the tests so clippy has less to complain about.

I’m about to edit the Rust index tests and the Python wire/provider tests. The new tests are focused on exact failure modes from the plan: JSON decoding budget, active row preservation, safe query pushdown, and bounded-provider metadata.

The core candidate query is now scalar-only until selected rows are loaded. I’m adding the regression tests next.

The Rust tests now cover the new bounded-window behavior. I’m mirroring the same contract at the Python boundary and adding provider-level assertions for query and viewport forwarding.

The Python wire reader already tolerates missing `index_window` data, so the test will check both the new query serialization fields and the typed window metadata rehydration.

I’m adding query-pushdown unit coverage separately because it’s the guardrail that keeps unsupported filters on the correctness path instead of accidentally using the bounded index path.

Next I’m extending the loader wiring test to assert the provider seam is actually used and that viewport/query metadata survives into the shared snapshot.

The provider tests now verify both injected-provider use and the direct provider’s bounded metadata. I’m adding the query-edit scheduling assertion and a bounded-prefix merge guard test next.

The existing filter-action test file is small, so I’m extending it in place for the new “refilter immediately, refresh asynchronously” behavior.

The old test name expected no async refresh after editing a query; that changed by design in this plan. I’m updating it to assert the new refresh scheduling contract.

I’m adding a regression around the bounded prefix not being “completed” by the previous full-history cache. That merge is valid for ordinary incomplete refreshes, but it would make the new viewport-limited prefix look unbounded.

I’m covering two async viewport edge cases now: a bounded result whose query is stale by the time it returns, and the near-end prefetch expansion trigger while navigating.

I’m adding one more loader-level test so the correctness fallback is explicit: safe scalar queries use the bounded candidate filter, while unsupported filters force the full-history path.

The new Python coverage is in place. I’m formatting the touched Rust and Python files before running focused tests, then I’ll broaden to the required `just check`.

Formatting is done. I’m running the focused Rust and Python tests for the new paths now; failures here should be narrower than the full repo gate.

The focused Python run found two test expectation issues, not implementation failures: one fake fixture didn’t actually leave a matching row past the cap, and shared snapshot metadata includes common paging fields. I’m correcting those assertions.

The test expectations are fixed. I’m rerunning the focused Python suite to catch any real integration issues before broad checks.

Focused tests are green. I’m running the broader core index test lane next, then I’ll rebuild the Python/Rust binding in this workspace before the required `just check`.

Core checks are green. I’m rebuilding the editable install now so the main Python workspace sees the updated Rust wire/schema before measurement and `just check`.

`just install` is still building the local Rust extension. I’ll let it finish rather than starting any checks against a stale binding.

No new output yet; the install is blocked on Cargo’s build lock and should continue once the other build activity releases it.

The install is still waiting on the shared Cargo build lock. I’m continuing to wait so the later validation uses this exact core checkout.

The Cargo build lock cleared and the Rust extension is compiling now. After this finishes I’ll rerun the focused Python tests against the rebuilt binding.

The extension build is still running without new output. I’m waiting for completion before moving on to validation.

The build has taken a few minutes but is still active. I’m not interrupting it because it owns the local extension artifact needed by the main repo tests.

Compilation has moved into the Python binding crate. Once it installs, I’ll verify both the changed unit tests and the startup-load timing.

No new install output yet; I’m still waiting on the binding build.

The binding build is still active. I’ll keep polling; no code changes are happening while this runs.

Still no new output from `just install`. It’s a long native build, so I’m continuing to wait for the command to finish cleanly.

The install is still running. I’m waiting rather than running parallel validation that could contend for the same build outputs.

`just install` completed and the local extension is installed. The transient LSP `cp/chmod/mv` lines appeared again but the installer reported the LSP installed and exited successfully, so I’m validating against the rebuilt environment now.

The rebuilt focused tests are green. I’m taking the same kind of timing sample as the plan requested, using the actual bounded first-paint inputs: current-project query, cached index, and a viewport-sized limit.

The bounded first-paint timing is now below the plan target: median 239.36 ms over seven samples for `project:sase`, `requested_limit=120`, cached Tier-1 index. I’m running the required `just check` gate now.

`just check` has passed the formatting and Ruff phases and is continuing through the remaining gates. I’m waiting for the scoped test and type/lint stages to finish.

`just check` failed only on mypy: the mixin calls `_schedule_agents_async_refresh`, which exists at runtime through the composed app but not on this mixin’s static type. I’m changing those calls to the project’s existing `getattr` mixin pattern.

The mypy issue is patched. I’m formatting that file and rerunning the focused gate before retrying `just check`.

The targeted mypy check is clean. I’m retrying the full `just check` now.

`just check` has cleared the early lint phases again. I’m waiting on the longer mypy/scoped test phases.

Mypy is clean; the check is now past the highest-signal static gate and continuing through the remaining validation.

The feature-flag and script lint phases passed. I’m continuing to wait on the scoped test selection and execution.

More repo lint phases passed. I’m still waiting on the remaining `just check` phases to complete.

`just check` now fails at Symvision: `_load_agents_from_disk_impl` is a private helper exported through the facade and no longer used locally. The project requires reading the Symvision memory before fixing that class of lint, so I’m doing that before the edit.

I’ve loaded the `sase_memory_read` skill. Now I’m reading the Symvision reference memory through the audited command, as required for this lint fix.

Symvision confirms the right fix: this is a dead private helper, not a whitelist case. I’m removing `_load_agents_from_disk_impl` and then rerunning the exact Symvision lane.

`rg` shows `_load_agents_from_disk_impl` has no non-test caller and no caller at all. I’m deleting just that dead helper.

The dead helper is removed. I’m formatting the touched helper and rerunning the failing Symvision command before retrying the full gate.

The exact Symvision lane is still running after the setup preamble. I’m waiting for its verdict before retrying `just check`.

Symvision is clean now. I’m rerunning `just check`; this should move past the previous failure and into scoped tests.

`just check` is past formatting and Ruff again. I’m waiting through the remaining static and test phases.

Mypy is clean on the full run. The gate is continuing through the later lint phases and scoped tests.

The feature-flag and script lint stages passed. I’m waiting for the remaining linters and scoped test selection.

The later lint phases are now clean through terminology checks. I’m continuing to wait on Symvision and then the test lane.

Symvision and the size lint are clean now. `just check` is into the remaining validation stages.

SASE validation passed. The core floor probe emitted its existing “stale_actionable” advisory, but the check continued and marked the validation phase complete. I’m waiting for the scoped test lane.

There’s no new output yet from the test phase. I’m continuing to wait for `just check` to finish rather than starting another validation pass in parallel.

The command is still running without additional output. I’ll keep polling until it exits so there are no orphaned validation processes.

Still waiting on the same `just check` run. It appears to be in a quiet test phase; I’ll report the final status once it exits.

The validation run remains active with no new output. I’m continuing to wait; no additional changes are being made.

No change in the quiet phase yet. I’m still attached to the running check and will continue polling.

The check is still running and quiet. I’m waiting it out so the final result reflects the actual repo gate.

Still no output from the running check. I’m continuing to wait for completion.

The validation process has been quiet for several minutes but is still running. I’m keeping the session open until it exits.

No new output. I’m still waiting on the active `just check` process and will not start a second one.

The check remains active without output. I’m continuing to poll; if it stalls indefinitely I’ll switch to the project’s monitor flow, but for now it is still attached.

The quiet phase has lasted long enough that I’m going to inspect the process tree, just to confirm whether it is running tests or waiting on a lock.

The quiet process is the scoped pytest lane (`pytest -n 13`), not a lock wait. I’ll keep waiting for that run to finish.

The scoped pytest lane is still running without new output. I’m continuing to wait on the active validation process.

No new test output yet. The scoped lane remains active; I’m waiting for completion.

`just check` reached the full test lane because the core identity changed. Six focused loader tests failed; I’m rerunning just those with full failure output so I can fix the behavioral regression instead of guessing from the summary.

The six failures share one symptom: synthetic planner rows are being produced where the existing tests expect concrete plan-family rows to stand alone. I’m inspecting the normalization path now; the regression is probably from how the new bounded/full-history loader call now reaches normalization, not from the index candidate tests themselves.

The failing assertions are in normalization tests that do not use the new bounded index path directly. I’m checking the actual diff around the loader and wire dataclasses now; a field-order or call-shape change is a likely root cause for this kind of indirect regression.

The synthetic planner decision itself is unchanged. I’m drilling into the guard inputs for the failing cases to see why `ensure_synthetic_planner_children` now believes there is no concrete planner child.

A direct call to `_apply_status_overrides` reproduces the status drift without the new viewport code involved. I’m checking the planner status policy now to decide whether this is a pre-existing broken invariant or a small fix needed to keep the required gate green.

The failing tests point at two concrete invariants: completed/retrying plan roots should not get display-only planner rows, and host-owned epic status should not be mirrored onto a concrete planner before an epic bead id exists. I’m checking the tests around that policy before making the smallest correction.

The artifact reload test expects even newly written `epic_bead_id` metadata to be copied, not to change the row’s visible status. I’m narrowing the fix to the planner-child policy instead of touching artifact loading.

There are other tests that intentionally expect `EPIC APPROVED` or `EPIC CREATED` when a real epic follow-up child exists. I’m checking those cases so the fix only affects lone roots and planner rows, not active epic child handoffs.

The smallest policy change is to skip display-only planner synthesis when the logical planner status would be terminal `DONE`, and to treat epic/commit plan actions as completed planner work rather than an active planner status. I’m patching that status policy now.

Planner synthesis now skips terminal logical children. I’m applying the epic/commit planner-status adjustment next, then I’ll rerun the exact six failures.

One ordering detail matters: the existing epic helper still runs before the new fallback, so I’m removing that planner-row epic override instead of leaving unreachable code. Active and completed `.epic` follow-up rows still use their separate handoff policy.

That helper is only used in `planner_child_status`, so I can remove it cleanly and keep epic handoff behavior on the real `.epic` child paths.

The planner-row epic override is removed; real epic child handoffs are untouched. I’m formatting and rerunning the six failing tests plus the adjacent epic-child status tests.

One adjacent test node name was wrong, so pytest aborted collection before running the set. I’m correcting the node and rerunning the same focused status tests.

The tale-status file does not have the exact adjacent node I expected, so I’m limiting this rerun to the previously failing tests plus the two real epic-child handoff tests I confirmed.

Two edge cases remain: a retrying root and a lone `approve` root still synthesize a planner. I’m checking where lone approved roots are expected to synthesize so I can gate this without breaking active plan handoffs.

There is no direct test asserting planner synthesis itself; the coverage is mostly “do not synthesize” plus real child handoffs. I’m going to gate synthesis to cases where there is an actual follow-up family child for approved planner statuses, and skip retrying roots.

I found the helper that can tell whether a parent already has a real family follow-up. I’m using that instead of keying this decision only off `plan_action`.

I’m adding a narrow synthesis guard: terminal logical planners, retrying roots, and approved planner statuses with no real follow-up child will not create display-only rows.

The synthesis guard is patched. I’m formatting and rerunning the focused status set again.

The retry failure is created before retry projection runs: the parent is still `FAILED` during normalization, so it was synthesizing a failed planner row. I’m extending the terminal-status skip to cover failed/rejected logical planner rows too.

The terminal-status skip is patched. I’m rerunning the focused status tests once more.

I’m picking up from the implementation state and re-running the focused tests that were in-flight at compaction. If those are clean, I’ll run the required repo check again and then submit the SASE final declaration.

The focused rerun is down to one status-policy failure: a live retrying plan still has a synthetic planner child. I’m going to inspect that projection path and make the skip condition match the retrying-family behavior the tests expect.

The skip inside `ensure_synthetic_planner_children` runs before the parent is promoted to `RETRYING`, so it never sees the retry state. The cleaner fix is to either project retry status before synthetic planner materialization or have the synthetic pass recognize the live retry fields directly.

I’m making a narrow change in the planner-child materialization guard: it will treat a live parent with `retry_status == "retrying"` as retrying even before the later root-mirroring pass writes the display status.

That guard still doesn’t eliminate the `plan` row, so the row is likely concrete, or the parent retry fields aren’t populated at that exact pass. I’m going to print the normalized fixture rows to see which artifact is producing the `plan` role.

The debug print shows the synthetic pass sees `runner_is_live=True` but `retry_status=None`; retry metadata is attached later. I’ll move the live-retry suppression to a signal available at that point, without changing terminal non-retry families.

At the synthetic pass, the only reliable live-retry signal is currently `runner_is_live`; `retry_state.json` is applied later in the disk helper. I’m checking whether moving retry-state hydration earlier is scoped enough, since that would let both the synthetic pass and root projection use the same metadata.

I’m adding the suppression where retry metadata is actually hydrated. It removes only synthetic planner rows whose root is a live retrying runner, leaving real family children and terminal retry history alone.

The live-retry row now prunes the synthetic planner after retry-state hydration. I’m rerunning the focused status set, then I’ll return to the viewport tests.

The status regression set is now green. I’m rerunning the viewport/direct-provider focused tests to make sure the additional pruning didn’t disturb the bounded-load path.

The targeted viewport and status suites are green. I’m starting the required `just check` now; it may take several minutes because the repo’s scoped test lane has been escalating to the larger suite for these changes.

`just check` has finished format and Ruff so far and is still running through the remaining lint/test gates. I’m waiting on the same session rather than starting a competing check.

Mypy is green. The check is still running through the project-specific validation and test selection steps.

The remaining lint gates are progressing cleanly: feature flags, script checks, waits, and changelog validation have passed. I’m continuing to watch the single `just check` run.

Symvision and the size checks are green now. The check is into SASE validation and the selected test lane next.

SASE validation passed. The check is now in the test-selection phase, which is the part that took longest on the earlier run.

The core-floor probe emitted its known stale-floor warning but the check advanced past it and marked committed plans green. I’m waiting on the Python test lane now.

No new output in the last interval, which usually means pytest is running. I’m continuing to poll the same check session.

The test lane is still quiet, so I’m letting it run. I won’t start a second test process against the same workspace.

Still waiting on pytest output from `just check`. The earlier full scoped run took several minutes, so this timing is within expectations.

There’s still no new check output. I’m continuing to wait on the running process; once it returns I’ll either fix the next concrete failure or move to final validation.

The check session remains active. I’m polling again with a larger output budget so we don’t lose the failure details if pytest reports a long summary.

No output yet; the process is still running. I’ll keep waiting on it until it exits so we have a definitive check result.

The long quiet section is continuing, which points to the expanded test lane rather than a hung lint step. I’m still attached to the original session.

Still no new output from `just check`. I’m continuing the wait; there’s nothing actionable until the test process reports back.

The check has now been in pytest for a while without output. I’m going to give it another interval before considering whether a monitored handoff would be more appropriate.

This has been quiet long enough that I’m checking the process tree once, just to distinguish a slow test run from a stuck child process. I’ll keep the original `just check` session alive while inspecting it.

That process-tree check only saw the short inspection shell, not the running PTY session. I’m checking globally for the `just` and pytest child processes so I can tell whether it’s still executing tests.

The process list confirms `just check` is running the expanded scoped pytest lane with four workers. I’m back to waiting on the original session for the actual test result.

No new pytest output yet. I’m continuing to let the expanded run complete rather than interrupting it.

The expanded pytest lane is still quiet and active. I’ll keep polling until it produces a pass/fail summary.

Still waiting on the test lane. The running process is expected; no failure details have appeared yet.

Another interval with no new output. I’m keeping the check attached and will act on the first concrete failure if one appears.

The test run is still active. I’m checking the original session again for completion output.

The long pytest segment continues. I’m still waiting; the session is not done yet.

Still no result from pytest. I’m continuing to poll the active `just check` process.

The check is still in the expanded pytest lane with suppressed progress output. I’m going to keep polling the same session; interrupting now would waste the run.

No completion yet. I’m still attached to the active session and waiting for the suppressed pytest lane to emit its summary.

The test process remains active. I’m continuing to wait; no failure output has been produced.

Still waiting on `just check`. The run is long, but it is still active and I have not seen a failure summary.

The check has been quiet for an extended period, so I’m going to inspect the pytest worker states briefly. That should tell me whether it is still consuming CPU or blocked in a specific child.

The worker inspection shows four pytest workers still using CPU, so the run is slow but not stuck. I’m continuing to wait on the active `just check`.

The expanded test run is still active. I’m polling again for the final pytest summary.

`just check` completed successfully, including the expanded scoped lane: 1,394 selected test files passed. I’m doing a final status/diff scan across the main repo and the linked core repo before the SASE final declaration.

The final status scan shows only the intended main repo changes and linked `sase-core` changes. I’m reading the SASE finalizer instructions now, then I’ll submit the required final declaration as the last action before reporting back.

I’m using the `sase_final` skill now. The next actions are finalizer context inspection and declaration submission; after a successful submit I won’t touch the worktree again in this turn.

The finalizer requires commits for both changed repositories. I’m submitting one manifest with a main-repo agents viewport commit and a linked `sase-core` windowed index commit.

Implemented the approved `agents_viewport_1.md` plan.

Main changes:
- Added bounded Agents viewport loading through the direct data provider.
- Added safe scalar query pushdown for `project:`, `cl:`, `model:`, `provider:`, and `type:`.
- Extended `sase-core` artifact index reads with window/filter metadata and delayed record JSON decoding until selected.
- Added stale async-result rejection, query refresh behavior, near-end prefetch, and bounded-prefix merge protection.
- Preserved live retry projection by pruning synthetic planner rows for retrying roots after retry metadata hydration.

Verification:
- `just check` passed, including the expanded scoped lane: `1394 of 3461` test files.
- Focused viewport tests passed: `42 passed`.
- Focused status regression tests passed: `8 passed`.
- Core checks from this run passed for `cargo check -p sase_core` and `cargo test -p sase_core agent_scan::index`.
- Bounded first-paint measurement improved from baseline `610.85 ms` median to `239.36 ms` median for `project:sase`.

SASE final declaration was accepted for commit.
