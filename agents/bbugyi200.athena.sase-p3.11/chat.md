# Chat History - ace-run (sase-p3.11)

- **TIMESTAMP:** 2026-08-17 23:06:03 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-p3.11

## Prompt

#gh:gh_sase-org__sase
%id(11, clan=sase-p3, bead=sase-p3.11)
%model:@medium
%auto
%w:sase-p3.4
%w(bead=sase-p3.4)
Can you complete the work for bead sase-p3.11? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-p3.11 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-p3.11`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-p3.11 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design file, and the relevant SASE skills so I can finish `sase-p3.11` without touching the parent epic.

The phase is an install-offer gate for missing required plugins. Next I’ll read the epic plan and related context.

Phase 11 is the missing-plugin install gate. I’ll inspect the existing chop/gate patterns and the phase-4 `plugins.required` code next.

The gate should follow existing flag/triage chops. I’ll read those specs, the required-plugins helper, and how chops are registered.

Stale-cleanup is the closer model—one gate per project—so I’ll read that chop, the gate adapters, and plugin-install next.

I'll map gate-kind registration, plugin install, and the existing chop tests so the new install-offer gate matches the rest of the system.

I have the gate contract shape. Next I’ll pin down project-root lookup, chop tests, and every registration list this new kind has to join.

I have the design. Next I’ll read a few remaining helpers, then implement the gate, chop, tests, and docs.

I'll add the gate modules first, then wire the chop, adapter, and tests.

Next I’ll add the tests and update the registry assertions that list every gate kind.

Satisfied projects were being marked changed every tick. I’ll fix that reconciliation path before running tests.

Install finished. I’ll run the new tests first, then the full `just check`.

Focused tests passed. Next I’ll run `just check` for the whole-repo lint and scoped test lane.

`just check` failed on stale `--epic-symbol` entries. I’ll read the Symvision rules, inspect this phase’s symbols, and clean them up.

The required plugins are broken editable installs pointing at missing checkouts. I’ll reinstall them from PyPI so validation can run.

Closed **sase-p3.11** (`Missing-plugin gate offering to install`). The parent epic **sase-p3** is still open.

Humans now get an install offer when a project’s `plugins.required` list is not satisfied. Agents still fail closed and never auto-install.

### What landed
- A five-minute `plugins_required` chop in the checks lane. For each enabled project it compares `plugins.required` to installed distributions and raises **at most one** `PluginsRequired` gate per distinct missing set.
- **Install** runs `sase plugin install <name>` for each missing requirement in the option command. If sase is not a `uv tool` install, that fails with the same message `sase plugin install` already prints and the gate stays pending. A successful install restarts axe (noted in the preview).
- **Dismiss** records the decision so the same missing set is not re-offered until it changes.
- The chop cancels the gate when the required set is satisfied.
- `fail_closed_required_plugins` / `RequiredPluginError` are now used from memory init, so those symbols are real consumers rather than phase whitelist leftovers.

### Verification
- Focused gate, chop, and registry tests: **75 passed**
- `just check` green, including an escalated full scoped suite
- `sase bead epic-symbols sase-p3.11` is empty

### Follow-up for the land agent
`PROPOSED FOLLOW-UP:` re-keyed a stale `Justfile` `--epic-symbol` from closed `sase-p1.5` (`glossary_entry_relations`) to parent `sase-p1` so `just check` would not go red. `sase-p1.7` still owns `GlossaryPanel` and should consume that helper.

I'll close bead `sase-p3.11` first (the close command is the publish check), then commit with the git-commit skill. Reading those skills and the current repo state now.

The working tree is this session’s phase-11 work. I’ll publish the close first (that command is the publish check), then commit.

The close command is still running. I’ll wait for it to finish before committing.

Close published (already closed, note appended). Next I’ll record the commit skill and create the stitch.

Rebase paused on a `Justfile` conflict with the glossary commit. I’ll resolve it, continue the rebase, then resume the stitch.

Upstream already consumed `glossary_entry_relations`, so I’ll drop that whitelist line and keep the rest of the file.

HEAD already dropped the glossary symbol. I’ll confirm the p3.11 symbols are gone, then finish the Justfile merge.

Rebase is clean. I’ll resume the stitch so it can push and finish bookkeeping.

Closed **sase-p3.11** (already closed; close republished and appended the verification note) and committed the missing-plugin install-offer work.

**Commit:** `e4f28dd57` — `feat(plugins): offer a gate to install missing required plugins`  
**Branch:** `master` is clean and in sync with `origin/master`.

Rebase onto `origin/master` conflicted in `Justfile`. Upstream had already consumed `glossary_entry_relations`, so that `--epic-symbol` line was dropped. The p3.11 symbols stay off the whitelist because this change uses them.

Parent epic **sase-p3** is still open.
