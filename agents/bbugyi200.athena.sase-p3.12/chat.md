# Chat History - ace-run (sase-p3.12)

- **TIMESTAMP:** 2026-08-18 01:05:09 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-p3.12

## Prompt

#gh:gh_sase-org__sase
%id(12, clan=sase-p3, bead=sase-p3.12)
%model:@small
%auto
%w:sase-p3.5,sase-p3.7
%w(bead=sase-p3.5)
%w(bead=sase-p3.7)
Can you complete the work for bead sase-p3.12? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-p3.12 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-p3.12`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-p3.12 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead workflow rules and the sase-p3.12 description so I can do only this phase's work.

Next I’ll load bead rules and pull the sase-p3.12 record so the phase scope is explicit.

The phase is the github task type plus mirror stamping. I’ll read the epic plan and related design next.

Phase 12 lives in sase-github plus this repo’s issue mirror. I’ll open the plugin repo through the repo skill and inspect the current task-type and mirror code.

I have the phase contract. Next I’ll inspect create/mirror APIs, the plugins.required error shape, and how other plugins register hooks.

I’ll check how research-artifacts registers hooks so the github task-type plugin matches that pattern.

I have the contract. Next I’ll add the github task type in sase-github and stamp it from the issue mirror.

I’ll add a transition test proving existing untyped mirrored beads still reconcile when the github type is missing.

I’ll keep `sase_github` importable on older sase by not pulling the task-type module into the package `__init__`.

Install pulled in the linked sase-github plugin. I’ll run the new tests next, then `just check`.

`just check` died on an unrelated feature-flag lint. I’ll confirm it’s pre-existing, then run the rest of the gates.

The flag lint is unrelated to this phase. I’ll run the remaining check stages and note the flag issue as follow-up.

Symvision flagged `require_github_task_type` as unused public API. I’ll read the lint rules, then make it private.

One failure is mine: the create test still treats `github` as an unknown type. I’ll inspect it and switch that case to a slug that is not installed.

No leftover epic-symbols for this phase. I’ll record the unrelated check failures as follow-up, then close only sase-p3.12.

Closed **sase-p3.12** (`done`). Parent epic **sase-p3** is still open.

## What landed

The `github` task type is now a real catalog member, and new mirrored issues get that type instead of an untyped task.

**In the linked `sase-github` repo**
- Registered `sase_task_types` entry point `github`
- Spec: `agent_creatable: false`, no extra fields, glyph `⑂`, accent `#B2B2B2`
- `when_to_use` says agents never create this type; the external issue mirror does

**In this repo**
- `apply_issue_mirror` stamps `task_type="github"` on new mirrored task beads
- If `github` is missing from the live catalog, the create path fails closed with `required plugin \`sase-github\` is not installed; run \`sase plugin install sase-github\``
- Existing untyped mirrored beads are left alone (no backfill)

## Verified

- Live registry reports `github` from package `sase-github`, `agent_creatable=false`
- `sase bead epic-symbols sase-p3.12` reported no leftover `--epic-symbol` entries
- sase-github task-type tests: 4 passed
- Mirror create/status tests plus the required-plugin message test: passed
- Isolated the degraded “not installed” render test so it no longer assumes `github` is unknown
- Escalated full suite: 32,982 passed after that render-test fix

`just check` still has two pre-existing reds I did not cause: feature-flag lint (`sase-pa` / `epic_resume_gate`) and home `sase memory init --check` drift. Those are recorded as `PROPOSED FOLLOW-UP` notes on sase-p3.12, along with one flaky procs-supervisor test that failed once then passed on rerun.

Changes are uncommitted in both this repo and the linked `sase-github` working tree. I did not commit; say if you want those landed.

I'll close the phase bead first, then commit the main workspace and the linked `sase-github` repo with the git-commit skill.

I'll inspect both working trees, then close the phase bead and commit each repo through the stitch workflow.

The main-repo diffs match this phase. Next I’ll inspect `sase-github`, run epic-symbols, and close the bead.

Epic-symbols are clear. I’ll inspect the linked repo from its checkout, then close the phase bead.

The close command is still running. I’ll wait for it to finish before committing.

The phase bead is closed. Next I’ll write commit messages and commit both repositories.

The main repo commit landed and is clean. Next I’ll commit the linked `sase-github` changes.

That commit ran in the already-clean main workspace. I’ll rerun it from the linked `sase-github` checkout.

I’m switching into the linked checkout and committing from there.

Both commits succeeded. I’ll confirm each working tree is clean before wrapping up.

Closed **sase-p3.12** and committed both working trees. Parent epic **sase-p3** is still open.

**Bead**
- `sase bead epic-symbols sase-p3.12` reported no leftover `--epic-symbol` entries
- `sase bead close sase-p3.12` succeeded (already closed; verification note recorded). No unpublished-close diagnostic.

**Commits**
- **sase** `118a60836` — `feat(external-mirror): stamp github task type on new mirrored issues`
- **sase-github** `a68b879` — `feat: register agent-uncreatable github task type`

Both repos are clean and even with `origin/master`. Agent-hood publication warnings are unrelated to these commits.
