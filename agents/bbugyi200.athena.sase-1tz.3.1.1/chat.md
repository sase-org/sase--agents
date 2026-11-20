# Chat History - ace-run (sase-1tz.3.1.1)

- **TIMESTAMP:** 2026-11-20 11:56:33 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1tz.3.1.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-1tz.3.1.1, bead=sase-1tz.3.1.1)
%clan(sase-1tz.3.1, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-1tz.3.1.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tz.3.1.1` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tz.3.1.1` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tz.3.1.1 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tz.3.1.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tz.3.1.1 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tz.3.1.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tz.3.1.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Reading the bead and plan for the `prompt_prose` wire phase; next I'll open sase-core and look at the origin enum.

Opening the sase-core repo to add the `PromptProse` origin variant.

Auditing Rust origin branch sites (merge `increments_uses`, cutover, index chips) before editing the enum.

Now the Python side: how sase treats `prompt_prose` today.

Rust audit done: only `increments_uses` branches on the enum; index chips and the bead read projection pass origin through. Editing `wire.rs` now.

Adding the core `ALL` round-trip test, a prompt_prose upsert test, and a binding-level validate_row test.

Now writing the Rust tests.

Compiles. Running targeted tests.

Rust side passes. Now the Python side: checking how this workspace's venv gets `sase_core_rs` so the contract test runs against the new binding.

Python design: a new `src/sase/sdd/artifact_link_origins.py` holding one origin table with derived subsets. Checking import weight of `sase.sdd` first.

Writing the origin module.

Pointing the call sites at the derived subsets.

Now the binding contract test. Checking where sdd artifact-link tests live.

Running the new contract test against the venv's current (old) binding first — it should fail for `prompt_prose`, proving it catches drift.

The test reproduces the exact production error ("unknown variant `prompt_prose`"). Now formatting, then rebuilding the venv binding from the edited sase-core and running sase-core's gate.

Contract test passes (21/21) on the rebuilt binding. Now running both repos' gates in parallel.

sase-core's gate passed. sase's check is still in its test lane, so I'll wait on it and do the skew-message investigation alongside.

sase's check passed too (scoped lane escalated to the full suite, all green). Confirming the summary, then taking the read-only "before" measurements on athena.

Now reading athena's live standing-alert store and the artifact-link outbox, read-only.

The standing store is empty right now. Checking the audit's F6 evidence to locate where the failing citations live.

Measuring athena "before" numbers (read-only): digest failures and pending outbox entries for the `research_commit_gap.md` citation family.

Key finding: the 3 publication-outbox items for this citation family are **quarantined** (attempts=3), so they won't retry on their own after install. Checking whether a replay command exists.

Measurements captured. Now checking docs for an origins list that needs `prompt_prose`, and the phase's epic-symbols.

Updating the docs that list origins (reference pages + CLI help), and adding the contract test to the rust-backend contract table.

Docs done. Before the final check, loading the `/sase_final` skill to see how the two-repo commit and pin move are declared.

Writing the bead notes now. First confirming the exact retry-key syntax for the after-install command.

Notes recorded. Re-running sase's `just check` inline on the final tree, since the docs and parser help changed after the first green run.

Final check is green (scoped tests 7m39s, all lint/docs stages passed). Closing the bead and submitting the declaration.

The pin is configured (`revision_pin: sase-core-revision.txt` in `sase/sase.yml`), so the host moves it when it commits both repos. Closing the bead and submitting.

I finished sase-1tz.3.1.1: sase-core now accepts `prompt_prose`, which removes the cause of the "unknown variant `prompt_prose`" publication failures. Checks passed in both repos and the bead is closed. The fix won't take effect on athena until after a global install, and the three stuck citation requests also need one manual retry command.

**sase-core**
- Added a `PromptProse` (`prompt_prose`) origin to `ArtifactLinkOriginWire`. It behaves like `prompt_ref`: it counts as an automatic citation, repeat citations add to the use count, and it is never relabeled as `prompt_ref`.
- Added an `ALL` list of every origin, with tests that round-trip each one, plus tests for prose citations and one at the Python-binding level.
- Only the use-count logic branches on origin in the Rust code. The other places I checked just pass the origin through.

**sase**
- New `src/sase/sdd/artifact_link_origins.py` holds `ARTIFACT_LINK_HOST_ORIGINS`, the one list of origins the host writes, along with the subsets derived from it. All 7 places that had their own hardcoded origin lists now use it.
- New `tests/sdd/test_artifact_link_host_origins_contract.py` sends every host origin through the real `sase_core_rs` binding. Against the old binding it failed with exactly the production error; against the rebuilt one all 21 tests pass. Any future origin added without Rust support will fail this test.
- Updated the docs and the `--origin` help text to include `prompt_prose`.
- The host commits both repos and moves `sase-core-revision.txt` automatically (it is set as the pin file in `sase/sase.yml`).

**Measured on athena (read-only)**
- Three publication requests for `sase-1tj.land` fail on `prompt_prose` for `plan:202611/research_commit_gap.md`. All three are **quarantined**, so they won't retry by themselves after install.
- No `prompt_prose` rows are stored, and there is no standing alert, because quarantine stopped the retries.
- After installing, run `sase agent sync -p sase -q`. The bead notes have the per-request retry commands and a one-liner to confirm the citations published once and no alert remains.

**About "artifact-reference wire is stale: expected 3, got 4"**
That message comes from an existing check that Python and the Rust binding are from the same install. It fires when they aren't, which is part of the update-race problems another phase owns, not this one. A similar version check wouldn't help artifact-link rows: adding an origin doesn't change their version number, and bumping it would invalidate every stored row.

There is still one gap. A newer sase running against an older installed sase-core-rs will still reject `prompt_prose`. The tool that checks the minimum core version only looks for missing functions, not missing origin values. I recorded a `PROPOSED FOLLOW-UP:` for making the supported origins something it can check.
