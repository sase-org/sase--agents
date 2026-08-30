# Chat History - ace-run (sase-vs.1)

- **TIMESTAMP:** 2026-08-30 08:08:27 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-vs.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-vs.1, bead=sase-vs.1)
%clan(sase-vs, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-vs.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-vs.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-vs.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-vs.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, the relevant SASE skills, and the design so I can complete `sase-vs.1` without touching parent close or status.

The bead is a medium phase for a shared wait-spec parser. I’ll load the plan, beads policy, and related memory next.

The glossary selectors were wrong. I’ll reread the required memory notes with the actual term names, then inspect the current wait and bead-work code.

I have the phase scope. Next I’ll read the wait-directive types, bead-work render/launch path, and existing tests so the parser and `--wait` option match current code.

I have the full shape of the change: shared parser, `--wait` on `sase bead work`, extra waits only on unblocked segments, and tests for parse, render, and CLI rejection. Implementing that next.

The workspace venv is stale, so I’ll run `just install` and then re-run the tests.

`format_wait_spec` is unused this phase by design — later epic launch uses it. I’ll read the symvision rules and re-key that symbol onto the still-open later bead.

I’ll whitelist `format_wait_spec` on `sase-vs.3`, the later phase that actually builds `--wait` argv.

Three tests failed, likely CLI goldens after adding `--wait`. I’ll pull the failure names and patch those snapshots.

Closed **sase-vs.1**. `sase bead work` now accepts `-w/--wait SPEC` and holds unblocked epic phases until those dependencies finish.

**What landed**
- Shared parser in `src/sase/wait_spec.py`: `parse_wait_spec` / `format_wait_spec` / `WaitSpecError`. Accepts agent names and `bead=<id>`, strips whitespace, deduplicates in first-seen order, and rejects empty entries, whitespace, empty `bead=`, and other `key=value` forms (`time=`, `runners=`, …).
- `render_multi_prompt(..., extra_waits=)` appends `%w:<agents>` and `%w(bead=<id>)` only on segments with empty intra-epic `waits_on` (root wave, and land when it does not wait on phases), after existing wait lines.
- The spec is parsed in `sase bead work` and forwarded through plan-file create, resume, and existing epic launches. A bad spec exits **2** before any bead or file mutation.
- Docs: `docs/cli.md`, `docs/beads.md`.

**Verification**
- Parser unit tests for agents, beads, mixed, dedup, and every rejection.
- Render tests: extra waits on root and land-only, not on dependents.
- CLI tests: invalid spec exits 2 without launching; dry-run preview stamps waits on the root wave only.
- `just check` passed (escalated to the full suite because the Justfile changed).

`format_wait_spec` is unused in this phase on purpose; it is keyed as `--epic-symbol "sase-vs.3(format_wait_spec)"` for the later epic-launch argv work. `sase bead epic-symbols sase-vs.1` reported no leftovers. Parent epic **sase-vs** was left open.
