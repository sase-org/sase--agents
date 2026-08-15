# Chat History - ace-run (sase-mf.2)

- **TIMESTAMP:** 2026-08-15 16:41:35 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-mf.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-mf, bead=sase-mf.2)
%model:@medium_worker
%auto
%w:sase-mf.1
%w(bead=sase-mf.1)
Can you complete the work for bead sase-mf.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-mf.2 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-mf.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I’ll use the SASE memory-read flow first because this task involves bead lifecycle operations, then I’ll inspect the assigned bead and its design context before editing.

The bead instructions require the project’s bead lifecycle memory, so I’m reading that audited note rather than opening memory files directly.

I’m checking the bead record and current tree state next so I can distinguish this phase’s work from any pre-existing edits.

The phase is `alias_config_contract`, dependent on `sase-mf.1`, and the workspace is clean. I’m reading the epic design file now to pin down the exact contract this phase owns.

The phase owns the Python-side contract: built-in alias shrinkage, three scalar launch fields, runtime routing, migrations, diagnostics, and tests. I’m locating the existing model-alias and launch-routing code before deciding the smallest complete edit set.

The search confirms the old aliases are spread through both runtime and presentation code. I’m narrowing to the runtime/config/state modules first, since this phase should leave the panel redesign and broad docs sweep to later phases.

The Rust binding is not importable in this workspace yet, which matches the project note that ephemeral workspaces need installation before checks. I’m still reading Python call sites first, then I’ll run `just install` before executing tests or probing bindings.

I’ve found the old behavior concentrated in `llm_provider` policy/config/resolution/state and the bead/tale routing helpers. The existing tests are also phase-specific, so I’ll update those alongside the implementation rather than relying on broad snapshots.

The default config and JSON schema still describe the old alias graph. I’ll update them to expose the new scalar launch fields and restrict built-in override guidance to the five size aliases.

The test suite globally freezes alias defaults, so I’ll update that fixture as part of the contract change. That keeps shipped target changes separate from graph-shape changes, which is exactly what this phase is doing.

To consume the new Rust routing functions safely, I need to inspect the linked `sase-core` repo through the required `/sase_repo` flow rather than reading the sibling checkout directly.

The core repo is opened through the audited repo command. I’m checking the binding names and expected wire shapes, then I can wire the Python helpers against them.

The Rust phase added `size_model_route(size)` and `select_epic_land_model(...)`, and the linked core is at `0.27.6`. I’ll bump the Python dependency floor accordingly so installs cannot resolve an older binding.

I hit the case-sensitive `Justfile` path and am checking the install/check recipes before running them.

I’ll also update the top-bar override helpers enough that the renamed default-launch setting no longer presents itself as a public `@default` alias. The full panel interaction redesign still belongs to the following phase.

I’m going to make the core contract edits now: shrink the bundled aliases to five size aliases, add launch-setting accessors/snapshots, and route bead/tale/default launches through those helpers.

The runtime built-in map now filters `model_aliases.builtin` to the five supported names, so stale built-in keys can still be diagnosed but no longer affect resolution.

I’m adding a thin Python facade over the new Rust model-route bindings, then the launch-setting module can use that without duplicating validation rules.

Next I’m adding the launch-setting accessors and snapshot. This gives no-model launches and epic landers a single defensive path for config defaults, temporary overrides, selector details, and provider resolution.

I noticed the new accessors should fail back to shipped defaults for malformed selector expressions, not just missing or non-string config. I’m tightening that before wiring call sites.

The default-resolution wrapper is now a compatibility facade over `llm_provider.default_model`; next I’ll move the public temporary override wrapper from the retired `default` alias key to the namespaced setting key.

I’m adding read-time migration for the machine-wide override state so old `default`, `*_worker`, and cheap/smart override keys are rewritten to the new setting or size keys without blocking launches.

That patch missed the exact docstring text, so I’m reopening the state module and applying the migration in smaller pieces.

The state module now knows the retired key map; I’m applying the actual normalization inside the v2/v1 read path.

I’m applying the same style of migration to round-robin cursor state, preserving compatible old cheap/smart and worker cursors under the new size aliases when fingerprints still match.

Now I’m removing the resolver’s special `@default` fallback path so `default` is no longer an implicit alias unless the user defines it as custom. The compatibility default-launch functions will route through the new scalar field instead.

I’m wiring bead phase/task/epic-land prompt rendering to the Rust route facade now, removing the Python size-to-worker alias table.

I’m updating launch metadata so no-model launches record `large` for the shipped `@large` setting, not the retired fictitious `default` alias.

The workflow executor also reconciles authoritative metadata after the real consuming resolution; I’m updating that path to record the same actual setting alias.

I’m flattening the alias view layer so the five built-in size aliases are top-level rows and the old automatic `worker` bucket disappears; custom buckets remain user-owned.

The indicator docstring had slightly different wrapping, so I’m patching the functional pieces directly.

The directive parser will naturally stop accepting retired aliases once `model_alias_names()` returns only five built-ins plus custom aliases. I’m tightening the error hint so it points to `@large`/size aliases instead of `@default`/worker aliases.

I’m updating doctor’s migration tables so stale config and alias references get explicit destinations: size workers move to size aliases, old lander/default aliases move to scalar fields, and smart/cheap names explain preservation instead of silently resolving.

I’ll keep the old `worker` and provider-coder guidance for earlier migrations, but point all size/model-role guidance at the new contract.

I’m picking up from the compact model-routing migration work: first I’ll verify the partial doctor patch and current diff, then finish the remaining config/schema/tests before running the repo checks.

The doctor file has only the first part of the migration patch applied; the old `default_model` warning and worker-alias guidance are still present. I’m going to replace the remaining legacy advice paths and then update the schema/default config to match the new scalar launch settings.

There’s broad test fallout expected because this is a public alias-contract change, but I’m keeping the production changes narrowly aligned with the phase. I’ve found the schema and default config still describe the retired role graph, so those are next.

The default config section starts much earlier than the range I first pulled; I’ll re-read that exact block before patching so the comments and examples stay coherent.

I’m about to edit the doctor check, default config, schema, and core dependency metadata. These are contract-facing files, so I’m keeping the comments explicit about the five public aliases and the three launch-setting fields.

I also found the lockfile pins `sase-core-rs` 0.27.5 while this phase consumes 0.27.6 bindings. I’ll bump the declared dependency first and then let the normal install/lock workflow verify whether the package metadata resolves cleanly.

I’m going to replace the doctor check’s core warning loop rather than patching each stale branch in place. The important behavioral change is that raw retired built-in entries are diagnosed from the raw config, while custom aliases with old names remain valid user aliases.

I’m editing the config doctor now. This will make `default_model` a supported launch field, turn `<size>_worker` diagnostics into `<size>` diagnostics, and stop treating old public names as reserved when the user intentionally defines them as custom aliases.

The doctor check is now using raw built-in entries for migration warnings, which is necessary because retired built-ins are intentionally filtered out of the runtime alias map. Next I’ll update the defaults/schema and dependency floor.

The schema/default config now expose the three scalar fields and only the five built-ins. I’m checking the doctor file for stale names and syntax before moving to tests.

The remaining stale doctor text is a reference-guidance branch for provider-specific coder aliases. I’ll update that and then move on to focused tests.

There’s also a small lint issue in the new Rust facade (`Any` is imported but unused). I’ll clean that while I’m in the production code.

I’m going to refresh the lock metadata for the new `sase-core-rs` floor before installing. If the package is not published yet, the local core override should still let dev install proceed, but the lock validator will tell us.

The lockfile resolved `sase-core-rs` 0.27.6 cleanly. I’m running `just install` now so the editable environment picks up the matching Rust binding before tests.

The install is compiling the local Rust core extension, which is expected after raising the binding floor. I’ll let that finish before running focused tests.

The Rust compile is still in progress and has reached the `sase_core` crate itself. No failures yet; I’m waiting for the editable Python install step after the wheel build.

The build is still running without new output. I’ll keep polling; once it completes I’ll run the focused alias/routing tests first instead of going straight to the full repo gate.

Still compiling with no new diagnostics. This is a local native extension rebuild, so the long quiet span is normal for the current step.

The build moved into the PyO3 wrapper crate (`sase_core_py`), so it’s close to the wheel/install phase now.

No errors from the wrapper compile yet. I’m continuing to wait; I won’t leave the install session running in the background.

The compile is still quiet. After it finishes, I’ll start with the doctor tests because they cover the migration guidance paths I just changed.

The install completed successfully with `sase-core-rs` 0.27.6. I’m updating the doctor tests now to match the new contract: `default_model` is valid, active built-ins are size aliases, and retired names are allowed only as custom aliases.

The doctor tests now exercise the compact alias behavior. I’m running that file to catch any logic mistakes before expanding to provider/runtime tests.

The first focused run failed before executing tests because `llm_provider.__init__` still re-exported the removed worker-bucket constants. I’ll align the package exports with the flattened alias view.

The package export now matches the flattened alias view. I’m rerunning the doctor test file to get real assertion failures, if any.

The next failure is the frozen test fixture still declaring the old alias graph. I’ll update that shared fixture once so all alias tests get the same five-size baseline.

The frozen defaults fixture is a shared contract fixture, so I’m reducing it to the same five size aliases and direct targets as the new parser expects. That should unblock all tests that rely on alias defaults.

The fixture now has only `xsmall` through `xlarge`. I’m rerunning the doctor tests; after that I’ll update the dedicated defaults tests that still assert the old fallback graph.

The doctor logic is passing except for one intentionally changed legacy-flat `coder` assertion. I’ll update that expectation to the new size-alias migration guidance.

I’ve corrected the final doctor expectation and will rerun that focused file once more before broadening.

The doctor suite passes. I’m moving to the default-alias parser tests now, since those still encode the old fallback graph shape.

I’m simplifying the parser tests to assert that every declared built-in is a direct size target. The parser can still validate fallback syntax for malformed fixture variants, but the shipped graph no longer has role fallbacks.

The defaults tests now assert the five direct target aliases. I’m running that file next.

The defaults parser suite passes. I’m broadening to the LLM provider tests now, which should expose the runtime resolution and temporary-override expectations that still need migration.

The broader collection hit two old-contract test imports before running assertions: the alias-view panel test still imports worker bucket exports, and the load-balancing defaults test still references `cheap`. I’ll migrate those next.

The alias-view panel tests are largely about the old built-in worker bucket, so I’m flattening those expectations to size rows plus user buckets. The load-balancing defaults tests will become size-alias rotation/fallback tests.

I’m replacing the old worker-bucket expectations with the flattened five-size ordering and custom-only bucket behavior. This keeps the Models panel data tests aligned with the phase requirement to remove the automatic worker bucket.

I’m rewriting the shipped load-balanced-alias tests around `@xsmall`, `@small`, `@medium`, and `@xlarge`. The old cheap/cheaper/cheapest aliases are now migration-only, not shipped defaults.

I deleted the old cheap/cheaper test file and am adding back the compact-size equivalent, preserving the rotation and fallback coverage.

The collection blockers are migrated. I’m rerunning the LLM provider suite to find the next set of runtime expectation failures.

The broad LLM provider run now gets through collection: 512 passed and the failures are mostly old test expectations around retired aliases. I’m going to update the high-signal runtime suites rather than chase each old alias name individually.

The main override-resolution test file is still written for `@default` and `@medium_worker`. I’m replacing those with `@medium`/`@large` alias behavior plus the namespaced `default_model` launch-setting override.

I’m replacing the override-resolution file with compact tests for the new behavior rather than preserving old role-alias cases. This should cut a large block of failures and also covers the namespaced launch default override directly.

The old file is removed; I’m adding the compact contract tests now.

The override-resolution tests are rewritten. I’ll run just that file to check the new expectations against the implementation.

That file passes now. I’m moving to the role-alias config tests, which are still the biggest old-contract block.

I’m replacing the old role-alias config suite with tests for the five built-in size aliases and custom retired-name behavior. This removes assertions about `epic_lander`, `smart`, and worker fallbacks from the runtime alias resolver.

The old role-alias suite is deleted; I’m adding the compact-size contract coverage now.

The compact role-alias suite is in place. I’ll run it before tackling the broader alias config/view failures.

The new role-alias tests pass. I’m moving through the remaining failures by suite: config alias parsing/resolution next.

The config parsing tests still assume arbitrary built-in entries are accepted. I’m updating them so only size aliases are valid under `builtin`, while user-defined aliases live under `custom`.

The parsing tests now separate size built-ins from custom aliases. I’ll run that file before rewriting the resolution suite.

The config parsing suite passes. I’m replacing the model-alias resolution suite with custom-alias chain tests plus launch override behavior for the active size aliases.

The old resolution suite is removed; I’m adding the compact equivalent now.

The resolution suite is now compact-alias based. I’m running the config parsing and resolution tests together.

Config parsing and resolution pass. I’m turning to the Models panel alias-view tests next, which still carry old ordering and fallback metadata expectations.

The view tests need the same treatment: five built-in rows, no default row, no built-in worker bucket. I’ll rewrite the old-heavy files to concise compact-contract assertions.

I’m replacing `test_alias_view.py` with a compact version that still covers ordering, selector metadata, custom aliases, and pool badge fields.

Adding back the simplified alias-view coverage now.

I’m adjusting alias-view metadata tests for custom buckets being user-owned and size aliases being the only built-in shadow candidates.

I noticed the manual metadata fixture still marked a `worker` member as a role alias. Since `worker` is now only custom/user-owned, I’m fixing that fixture classification.

I’m updating alias-view override tests from `medium_worker` to `medium`; the launch-default override is no longer represented as an alias row, so that expectation changes too.

The override view tests now target `medium` and treat launch-default overrides separately from alias rows. I’m fixing the remaining panel-row assertion for custom coder source.

I’m rerunning the alias-view group after the compact-contract updates.

Only one alias-view metadata count was still assuming the worker bucket lived in the built-in section. I’ll correct that user-section count.

I’m rerunning the alias-view group to confirm it’s clean.

Alias-view tests now pass. I’m rerunning the full LLM provider suite to see what remains after the main contract migrations.

The remaining load-balancing failures are mostly because test helper aliases named `pool`/`fallback` were configured under `builtin`, which now filters non-size names. I’ll move those helper aliases to `custom` in the tests.

I’m moving the generic `pool` helper into `model_aliases.custom`; that should fix both selector snapshots and pool rotation tests without changing production code.

I’m updating the few load-balancing tests that construct their own ad hoc `pool`/`focused` aliases to use custom alias entries.

I’m applying the same custom-alias setup to the load-balancing state tests.

I’m moving ordered-fallback helper aliases (`fallback`, `outer`, `inner`, etc.) into custom alias config as well.

The ordered-fallback patch was broad, so I’m checking that file for malformed dict literals before running it.

The ordered fallback test file is syntactically fine. I’m moving provider-disable routing aliases to custom entries and changing the default override test to use `default_model`.

I’m updating the temporary override state tests to expect namespaced launch-setting keys like `setting:default_model` and migrated `epic_lander_model`.

I saw the `test_temporary_override_phase2.py` snippet was interleaved by the multi-read output, so I’ll inspect that file directly before patching it.

The override-state behavior is intentionally migrating retired launch aliases to namespaced setting keys, so I’m changing the tests to assert those canonical keys.

I’m applying the same namespaced default key updates to the default temporary override tests.

In the phase2 invocation tests I’m switching the explicit alias override from `@medium_worker` to `@medium`, and expired default state edits to `setting:default_model`.

I’m updating the remaining expired-default override test to mutate the namespaced key.

Next I’m updating registry default-resolution tests from the retired `@default` alias to the scalar `llm_provider.default_model` path.

The registry tests now need to assert `default_model` behavior directly: configured scalar, shipped `@large`, invalid fallback to shipped default, and temporary launch override separation from `@default`.

I’ve migrated helper config and default-resolution tests. I’m running the remaining failing groups together to see what’s left.

Only one provider-disable test was monkeypatching an old internal helper. I’ll use the public `set_temporary_override` path instead.

I’m rerunning the remaining migrated groups to confirm they’re all clean.

The remaining failure exposed a production gap: scalar `default_model` accepted selector syntax but wasn’t actually evaluating it as a selector. I’m fixing `model_launch_settings` so direct selector expressions in launch fields use the same availability/fallback machinery.

I’ve added direct selector evaluation for scalar launch fields. I’m rerunning the migrated group that caught it.

The selector fix and migrated tests pass in the targeted group. I’m rerunning the full LLM provider suite again.

The full LLM provider suite now passes. I’m moving to bead rendering and xprompt/model-completion tests that reference phase sizes and alias completions.

I’m picking up from the already-applied routing changes and checking the remaining test surface outside `tests/llm_provider`. First I’m going to find lingering references to retired aliases and rerun the focused failures with smaller output.

The remaining failures are mostly old expectation text: phase routing now emits `@small`/`@xlarge` instead of worker and lander role aliases, and completion tests still expect the retired implicit aliases. I’m updating those tests next, then I’ll run the model panel suite to catch any UI-side assumptions.

I’m making the test edits now. The production behavior is already emitting the new scalar and size routes; these patches just make the expectations match the compact alias contract and exercise the new scalar lander config path.

The bead rendering and completion expectations have been updated. I’m rerunning those focused tests now before moving to the Models panel tests.

Those focused tests are green. Next I’m running the Models panel tests, which are more likely to still mention retired buckets and aliases.

The panel failures are also old fixtures: they still synthesize `default`/worker rows and a built-in `worker` bucket, but the new UI data layer is flat with five built-in size aliases and only custom buckets. I’m reading those test helpers and adjusting the fixtures without changing the panel behavior.

The helper fixtures still manufacture the retired alias set, which would keep causing follow-on failures in other panel suites. I’m going to compact those helpers to `xsmall` through `xlarge` first, then adjust the few tests that were specifically about the removed built-in worker bucket.

I’m rewriting the panel navigation tests around the flat alias list. The key change is that `xsmall`/`small`/`medium`/`large`/`xlarge` are navigated directly; bucket navigation remains covered by user-defined buckets like `research`.

The top-level panel flow tests are now on direct aliases. I’m updating the old “worker bucket” cases into direct size-alias navigation cases, while leaving custom-bucket coverage intact.

The navigation tests now use direct size aliases. I’m also updating the standalone bucket rendering assertions so synthetic custom buckets reflect the new ownership rule: there are no built-in model buckets anymore.

The panel rendering/navigation fixtures are patched. I’m rerunning those panel suites to catch any row-index or label mismatch from the flat layout.

The initial panel suites are green. I’m broadening to the rest of the Models panel tests now, because helper changes can expose expectations in edit, override, effort, and provider-routing flows.

The broader Models panel tests are green. I’m scanning for any remaining source-level references to the retired public alias names so comments, schema text, and diagnostics don’t advertise the old contract.

The scan found more test files with old expectations around bead work/task rendering and config schema examples, plus one stale default-config comment. I’m going to update those next; source references that are explicitly migration diagnostics or compatibility constants can stay.

I’m updating schema and bead-route tests now. The schema change is substantive: `llm_provider.default_model` is no longer obsolete, so that test should validate the new scalar fields rather than reject them.

I found the remaining bead-route snapshots and plan previews. I’m replacing worker/lander aliases there with the direct size aliases and scalar lander defaults.

The dry-run and frontmatter tests are updated. I’m applying the same direct-size route expectations to the plan-file preview tests.

The plan preview expectations are updated. I’m removing one remaining retired explicit alias value in a bead-rendering test so the suite no longer normalizes around `@smart`.

The bead-route test snapshots are patched. I’m running the bead work-related tests now to catch any remaining CLI preview mismatch.

The bead and schema focused tests are green. I’m doing another targeted scan now; remaining hits should mostly be compatibility migration code or tests that deliberately use arbitrary alias names, but I’ll clean up stale user-facing strings where they remain.

The remaining source hits are either migration tables or generic “default provider” wording, except a few stale docstrings/comments. I’m cleaning those before running the full check.

I found stale comments in the LLM provider docs and Models panel edit helper. I’m patching those; the migration constants and retired-key diagnostics are intentionally left in place.

The stale provider comments are cleaned. I’m also updating the remaining compatibility helper docstring so it is clear `default` is retained only for old callers.

I’m going to run the other test groups that still mention old aliases. Some of those names are deliberately arbitrary test aliases, but this will separate harmless examples from real broken expectations before the final `just check`.

The extra failures are test setup issues from the compact contract: ad-hoc aliases now belong under `model_aliases.custom`, and no-directive routing is controlled by `llm_provider.default_model`. I’m updating those tests rather than changing production back toward the retired alias graph.

I’m patching the invoke and indicator tests now: custom pools move under `custom`, configured no-directive routing uses `default_model`, and the launch-default pill no longer says `@default`.

Next I’m updating the top-bar override test to use the namespaced launch-default override key, so the alias pill only sees non-default aliases/settings.

The launch preview override parser test also used retired alias names. I’m switching it to override `medium` and `large`, with `@small` as the reference target.

I’m updating the AXE follow-up metadata tests to expect `@small`, since coder follow-ups now route through the small size alias directly.

The reasoning-effort metadata tests need the same semantic updates: no-model launches now record `large`, and ad-hoc pools are custom aliases. I’m patching those assertions and cursor checks.

The failing focused tests are patched. I’m rerunning the same groups to verify the compact alias setup works through invoke, metadata, and top-bar rendering.

The invoke and AXE groups are green. The metadata persistence file has a simple indentation typo from the cursor-key patch; I’m fixing that and rerunning the group.

The metadata group is green now. I’m running the remaining small groups from the scan that are most likely to encode old alias names in assertions.

Two more tests were using `medium_worker` as an override key, which now fails before value validation. I’m changing those override keys to `medium` so they continue to test branch-local override preservation and unroutable values.

Those two override-key tests are patched. I’m rerunning the directive and doctor groups to verify.

The remaining focused groups are green. I’m doing one more scan plus formatting/lint preflight so `just check` has fewer mechanical failures.

One source template still advertised worker aliases. That’s a generated-memory template in the repo, not a live memory file, so I’m updating it to the five size aliases.

I’m running the model picker and directive extraction/completion tests now, since they still have many old alias rows in their fixtures.

I’m picking up from the existing implementation state. I’ll first re-run the truncated test groups in smaller chunks, then fix any remaining legacy-alias expectations before the repo-wide check.

The broad text scan is noisy because it catches ordinary “default” usage, so I’m using the targeted test failures as the main signal now. The model-picker test is still running, and I’m checking whether any earlier command got stuck.

The first remaining failure is a model-picker dependency test still constructing the removed implicit alias graph. I’m narrowing that test to the new five built-ins plus a custom configured chain.

The helper itself still seeded the old built-in catalog, so I’m updating that shared fixture too. That should make the picker assertions align with the real alias list instead of masking old names in tests.

I’m going to make a scoped test-fixture edit now: replace the old public alias catalog with the five size aliases and adapt the picker assertions around `@medium`/`@large`.

The picker fixtures now reflect the compact alias contract. I’m rerunning that file and moving through the remaining previously truncated groups one at a time.

The parser failures are expected stale fixtures: `%model` override keys still use `medium_worker`. I’m converting those tests to the new `medium`/`small` keys and removing a leftover `smarter` default expectation.

For no-model metadata, the expected alias should now be the scalar launch default `@large`, not the retired `@default`/smart chain. I’m patching only those stale assertions and keeping the retired-worker negative test intact.

One chunk missed because the local test text differs slightly, so I’m reading the exact surrounding lines and will apply the replacements against the current file.

Those stale parser and metadata expectations are patched. I’m rerunning them along with the next two small suites that were truncated earlier.

The approve-options modal behavior is already routing to `@small`/`@medium`; only two assertions still expect worker aliases. I’m updating those expectations.

The approve modal assertions now match the new direct size aliases. I’m rerunning that file plus the broader model-panel group that was previously truncated.

The previously truncated test groups now pass. I’m doing one more targeted scan for retired alias tokens so I can separate intentional migration/diagnostic coverage from stale expectations.

Most remaining hits are unrelated “cheap/default” words or intentional migration diagnostics. One source comment still says unqualified runs use `@default`, so I’m checking that area for stale user-facing wording before formatting.

A few tests that passed still carried old alias names in sample data and snapshots. They are not failing, but they make the contract less clear, so I’m cleaning the local fixtures and one stale source docstring before the final check.

I’m applying mechanical fixture cleanups now: generic edit-helper tests will use `medium`, provider-routing samples will use current aliases, and the provider advisory docstring will refer to launch defaults instead of `@default`.

I’m updating the edit-helper tests similarly from `medium_worker` to `medium`; these are generic config-edit tests, so using a current built-in makes their fixtures match the shipped alias map.

Only a lexical directive-extraction test still uses old alias spelling now. I’m updating that sample to the current aliases; it does not change parser behavior.

The last fixture cleanup is in place. I’m rerunning the modified model-panel and directive extraction tests, then I’ll move to formatting and the required `just check`.

The cleaned-up targeted suites pass and whitespace checks are clean. I’m running the repo formatter next, then the mandatory `just check` gate.

Formatting made routine changes and surfaced one lint issue in the new launch-settings code: a `zip()` needs an explicit `strict=`. I’m fixing that and then I’ll rerun the formatter.

I’m editing the lint failure directly by marking that selector-member zip as strict, since the three sequences are built from the same selector parse.

The lint fix is in. I’m rerunning `just fmt` so the formatter and ruff fixes settle before verification.

Formatting is clean. I’m checking the diff shape now, then I’ll run `just check` with the linked Rust core path set so the Python package uses the updated core bindings.

The diff is broad but centered on the alias contract, launch settings, docs, and tests; `git diff --check` is clean. I’m starting `just check` now with `SASE_CORE_DIR` pointed at the opened `sase-core` checkout.

`just check` is underway and has already cleared formatting, keep-sorted, and ruff. I’m waiting on the remaining type and scoped test gates.

`just check` stopped at mypy. The failures are type annotation issues around the new launch-setting literals, plus one alias-view empty-frozenset annotation and one doctor variable narrowing issue; I’m fixing those now.

The literal-field errors come from constants inferred as plain `str`; I’m moving the `LaunchModelField` type before the constants and annotating them. The doctor error is a reused `message` name with a narrower inferred type.

I’m applying those type-only fixes now: annotated launch-setting constants, an explicit empty bucket set type, and a renamed retired-alias diagnostic variable.

Those mypy fixes are in. I’m rerunning the formatter quickly, then I’ll rerun `just check`.

The formatter still passes after the type fixes. I’m rerunning the full `just check` gate now.

`just check` has now cleared mypy as well. I’m waiting on the remaining lint gates and scoped tests.

The auxiliary lint gates are passing too. The command is still running, likely in test selection/scoped pytest now.

`just check` is down to Symvision. Since this repo has a specific Symvision workflow, I’m reading that memory note before changing symbol visibility.

The Symvision note says to prefer privacy/deletion over whitelisting when symbols only feed local code or tests. I’m inspecting the new facade and registry wrappers to decide which should become private or be removed.

For the facade, I can make the internal route payload types/private helper private and keep only the public functions actually consumed. For the registry default wrappers, the real non-test path now goes through `model_launch_settings`, so I’m removing the unused compatibility wrappers and retargeting tests to the live API.

I’m editing the facade/registry now: route payload TypedDicts and the direct size-route helper become private, and the registry compatibility functions are removed in favor of the launch-settings API already used by production.

The combined patch did not apply cleanly against the formatted registry file, so I’m splitting it into smaller patches against the exact current text.

The facade visibility cleanup applied. I’m removing the unused registry wrappers and adjusting the test import/calls to the launch-default API.

The dead registry wrappers are removed. I’m retargeting the registry-resolution tests to import the same launch-default functions production uses.

The symbol fixes are in. I’m running the formatter and the Symvision lint path directly before another `just check`.

Formatting stayed clean. I’m running Symvision directly now so we can confirm the previous failure is gone before spending another full check run.

Symvision is clean now. I’m doing one targeted registry test rerun for the wrapper removal, then I’ll rerun the full `just check` gate.

The registry tests and diff whitespace check pass. I’m running the full `just check` again now.

The final `just check` run has cleared formatting, keep-sorted, and ruff. I’m waiting through mypy, Symvision, and the scoped test lane.

Mypy and the auxiliary lint gates have passed. The command is still running in the remaining checks.

`just check` now only fails because changing the generated memory template makes `sase/memory/sase_sizes.md` need regeneration. Memory files are protected by the project instructions and the user did not explicitly authorize a memory update, so I’m going to keep the canonical memory untouched, revert the template change that triggers the check failure, and record the memory refresh as a proposed follow-up on this bead.

I’m reverting only the generated-memory template wording so the protected canonical memory remains consistent with its current generated source. I’ll note the memory documentation update separately on the bead for the land agent to triage.

I’m checking that the memory template is back to the repo baseline and recording the protected-memory documentation refresh as the bead follow-up note instead of editing memory files.

The template diff is gone. The bead-note command is still completing, so I’m polling it before rerunning validation.

The note write has not returned yet, likely waiting on the bead store lock. I’m giving it a little more time rather than starting competing bead commands.

The proposed follow-up note is recorded on `sase-mf.2`. I’m rerunning formatting once more after the revert, then the full check again.

Formatting remains clean and memory files stayed unchanged. I’m running `just check` again; this should now get past the SASE validation gate.

The rerun has cleared formatting, ruff, mypy, and several repo lint gates. I’m waiting on the remaining validation, Symvision, and scoped tests.

Symvision and the size checks now pass. The command is still running in validation/test selection.

SASE validation is clean. The core-floor probe reports the new Rust capabilities are on the opened core commit but not yet in a tagged release; the check is still continuing, so I’m waiting for the final status before deciding whether this needs a bead note.

No new output yet; the check is still running, likely in the scoped pytest lane.

The scoped lane is taking longer than the lint stages but is still active. I’m continuing to poll it rather than interrupting the verification run.

Still no new output from the running check. I’m giving it another interval; if it appears stuck rather than slow, I’ll inspect the process before taking action.

The check has been quiet for several minutes. I’m inspecting the process tree from a separate command to see which subcommand is still running.

That process lookup matched my inspection command rather than the check. I’m listing the relevant `just`/pytest/test-selection processes directly.

The live process is the scoped pytest lane (`pytest -n 14`) and it has been running a little over four minutes. That is long but plausible for the selected closure, so I’m continuing to wait.

The full suite ran and surfaced 26 stale expectations. They cluster around alias override indicator fixtures, model completion candidates, follow-up prompt/model selection, and pooled default-launch behavior. I’m rerunning those files in smaller groups to get exact assertions and patch them coherently.

The first three files are simple stale fixtures: `medium_worker` should be `medium`, `@default` completion should not exist without a configured alias, and pooled-default tests should use `large` rather than retired `smarter`. I’m patching those now.

I’m applying the stale-fixture updates in those three files: current alias names, launch-default override key, no implicit `@default` completion, and the shipped `@large` pool for default launches.

Those first stale fixtures are patched. I’m rerunning the follow-up/model-selection failure group next to see the exact expectations there.

The follow-up failures are all old worker-alias expectations. One effort test needs to distinguish config default effort from the new `@large` alias effort; I’ll make that test pass an explicit provider so it exercises the config-default path it names.

I’m patching the effort and follow-up tests now: explicit-provider path for config default effort, direct size aliases in prompts, and `medium` as the metadata alias.

That follow-up/model-selection patch is in. I’m rerunning the coder-prompt and question follow-up files to catch their stale prompt-prefix assertions.

The alias indicator/completion/pool group now passes. The remaining coder-prompt and question failures are direct `@small_worker` assertions, so I’m updating those to `@small`.

I found a few more direct `@small_worker` assertions in the same follow-up files. I’m replacing those with `@small` while leaving negative `@worker` checks intact.

The remaining prompt-prefix patches are in. I’m rerunning all previously failing targeted groups together now.

The failing targeted groups now pass. I also see two stale passing fixtures in the same scan, so I’m cleaning those before formatting.

I’m replacing those remaining local samples with `medium`; the reserved `@default` tribe tests are unrelated and should stay as-is.

The remaining stale samples are cleaned. I’m running formatting and a compact targeted rerun before another full `just check`.

Formatting and the compact targeted rerun pass. I’m checking diff whitespace and then running the full `just check` again; the prior full-suite failures should be covered by the targeted fixes.

Whitespace is clean. I’m starting the full `just check` again; because the diff touches pyproject and generated docs, this still escalates to the full suite.

The new full check has cleared formatting, ruff, mypy, and script lint. I’m waiting on the rest of the gates and the full-suite lane.

The auxiliary lint gates are still passing. I’m continuing to poll through validation and tests.

The core-floor probe now sees those Rust capabilities in published `sase-core` v0.27.7, while the Python floor is still 0.27.6. I’ll let this check finish, then update the dependency floor and lockfile to v0.27.7 before the final verification run.

The full-suite lane is running now with no new output yet. I’m continuing to wait for its final status before touching the dependency files.

Still no new output; the process tree previously showed this stage is the full pytest lane, so I’m letting it continue.

The full-suite lane has been quiet for several minutes again. I’m checking the process tree to confirm it is still active and not wedged.

The process tree confirms this workspace’s `pytest -n 14` lane is active at about 3.5 minutes. I’m waiting for completion.

Still no output, but the full suite routinely takes several minutes under xdist. I’m giving it another poll interval.

`just check` now passes, but it emitted an actionable core-floor warning: the needed Rust functions are in published `sase-core` v0.27.7 and the Python floor is still v0.27.6. I’m updating the dependency floor and lockfile to v0.27.7, then I’ll rerun the check so the final state has no stale floor warning.

I also recorded a bead note for the core release dependency context, since it was discovered during verification. The note command is still completing; I’ll wait for it before editing dependency files.

The dependency context note is recorded. I’m bumping the Python dependency floor from `sase-core-rs>=0.27.6` to `>=0.27.7` and refreshing the lockfile.

The pyproject floor is updated. I’m refreshing `uv.lock` for `sase-core-rs` now.

The lockfile now resolves `sase-core-rs` v0.27.7. Since the dependency changed, I’m reinstalling the editable environment before rerunning checks.

`just install` tried to build a local linked `sase-core` checkout that is still version 0.27.6, so it rejected the new floor. I’m checking the install recipe and core checkout handling; the clean path is either to point install at an updated core checkout or let it use the published v0.27.7 wheel.

Both local core checkouts are still Cargo version 0.27.6. To verify against the published v0.27.7 floor without editing another repo, I’m going to run install with `SASE_CORE_DIR` pointed at a nonexistent path so the recipe skips local Rust builds and installs the published wheel from the lockfile.

The environment now has published `sase-core-rs` v0.27.7 installed. I’m checking the dependency diff, then I’ll run the full check once more using the published wheel path.

The dependency floor and lockfile now both say v0.27.7, and whitespace is clean. I’m starting the final full `just check` with local core builds disabled so it verifies against the published wheel.

The final check has cleared formatting, ruff, mypy, and script lint. I’m waiting on the remaining validation and full-suite lane.

The remaining lint gates, including Symvision, are clean. Validation and the test lane are still running.

SASE validation passes now without the core-floor stale warning. The command is in the final test lane.

No new output yet; this is the full-suite pytest lane again. I’m continuing to wait.

The test lane is still active and quiet. I’m polling again; the previous full-suite run took a little over five minutes.

Still no output; I’m checking the process tree once more to confirm it is still the expected pytest process.

The expected pytest process is still active at about 5.5 minutes. There are other agents also running checks, so this may be slowed by contention; I’m waiting for ours to finish.

The final `just check` passed, including the full-suite escalation, using the published `sase-core-rs` v0.27.7 wheel. I’m doing one last status check to ensure no protected memory files changed, then I’ll close only `sase-mf.2` with the verification note.

No protected memory/provider instruction files are modified. I’m closing only `sase-mf.2` now with the verification details.

Completed and closed `sase-mf.2`.

Implemented the compact model alias contract: five built-ins (`@xsmall` through `@xlarge`), scalar launch settings (`default_model`, `epic_lander_model`, `big_epic_lander_model`), Rust-core-backed size/epic-land routing, retired-alias migration/diagnostics, updated TUI/completion/override behavior, docs, and tests. Also bumped `sase-core-rs` to `>=0.27.7,<0.28.0`.

Verified with:
`just fmt`
`git diff --check`
targeted pytest suites
`SASE_CORE_DIR=/tmp/sase-core-not-present just check` — passed, with full-suite escalation.

I did not edit protected `sase/memory/*` files. I recorded a `PROPOSED FOLLOW-UP` note on the bead for updating the SASE size memory docs once explicitly authorized.

I’ll handle the finalizer path now: verify/republish the bead close as instructed, then use the SASE commit workflow rather than raw `git commit`. I’m reading the relevant SASE skill instructions first so I don’t bypass the project’s lifecycle rules.

The commit skill requires an explicit usage marker and a clean review of the dirty tree before committing. The bead memory rule also applies because I’m about to close or re-close the phase bead.

I’ve loaded the bead lifecycle note. I’m re-running the close command exactly as the finalizer requested; if it reports a local-only close, I’ll run the remediation it prints rather than treating the local event as sufficient.

The close command exited successfully and added a note to the already-closed phase bead. I’m reviewing the dirty tree now so the commit includes only the intended alias-contract work and bead close evidence.

The dirty tree is broad but matches the phase scope: model alias runtime/config/UI/docs/tests plus the dependency lock. The branch is behind upstream, which the stitch workflow is designed to handle after creating the local commit.

The focused diff confirms the public contract change: new scalar launch fields, five built-in size aliases, no protected memory files touched, and whitespace is clean. I’m checking the two new modules before writing the commit message.

The new modules are in scope: one thin Rust routing facade and one launch-setting resolver/snapshot layer. I’m writing a breaking-change commit message now because this removes shipped built-in aliases and changes the public config contract.

There is an existing temporary commit message file from the earlier pass, so I’m replacing its contents with the message for this final commit rather than creating a second file.

I’m overwriting that stale message with one that matches the Python-side compact alias contract and dependency bump in this tree.

The commit message is ready. I’m invoking the SASE commit wrapper now; it will stage the full dirty tree, create the commit, and handle the required sync/rebase path for this branch.

The commit hook failed before creating a commit because the linked local `sase-core` checkout is still at `0.27.6`, while this change intentionally verifies against the published `sase-core-rs` `0.27.7` wheel. I’m retrying the preserved commit message with the same published-wheel path used for the passing check.

The wrapper reports that the create-commit dispatch completed successfully, but the command session is still open. I’m polling it to completion before checking branch state.

The commit succeeded; only prompt archive publication was deferred by an agent sync lock. I’m checking the repo status now to confirm the working tree and upstream state after the stitch workflow.

The branch is clean and no longer ahead or behind its upstream after the commit workflow. I’m grabbing the commit id so the final summary can be concrete.

Completed the finalizer.

Committed the `sase-mf.2` work as:

`2fcca46eb feat!: replace role model aliases with size launch settings`

Also re-ran the required bead close command; it reported the bead was already closed and added the verification note.

Verification from the completed work:
`SASE_CORE_DIR=/tmp/sase-core-not-present just check` passed with full-suite escalation.

Current repo status is clean and aligned with `origin/master`. The commit workflow did warn that prompt archive publication was deferred because the agents sync lock was busy, but the primary commit succeeded.
