# Chat History - ace-run (sase-zl.8)

- **TIMESTAMP:** 2026-09-11 15:22:01 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-zl.8

## Prompt

#gh:gh_sase-org__sase
%id(8, clan=sase-zl, bead=sase-zl.8)
%model:@medium
%auto
%w(bead=sase-zl.7)
Can you complete the work for bead sase-zl.8? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-zl.8 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-zl.8`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-zl.8 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design file, and the SASE skills needed to complete this phase.

The prepare phase is host-sealed completion intents. I’ll inspect prior phases, the current continuation code, and sase-core next.

I'll open sase-core and inspect the continuation contracts plus the finalizer and monitor-start paths.

sase-core is open. Next I’ll inspect continuation contracts, finalizer bindings, and how earlier phases structured this work.

I have a clear picture of the prepare-phase contract. Next I’ll add the Rust schema and validation, then the Python CLI, observation, and single-use monitor binding.

I'll add the Rust completion-intent module first, then wire it through PyO3 and Python.

The seal digest used the wrong map type. I’ll switch it to string-keyed JSON and export the module.

I’ll add the host observation layer and `sase final prepare`, then wire single-use binding into monitor start.

just check failed on a pre-existing mypy error in continuation budget. I’ll apply a minimal type fix so the gate can run.

Closed **sase-zl.8** (Prepare conditional completion declarations). Host-sealed, single-use completion intents are in place; they do not submit, commit, or end the turn.

**What landed**
- **sase-core:** versioned conditional-completion schema with seal, preview, single-use bind, and failed-start rollback. First-party commands are exact `just check` / `just check-full` only.
- **SASE:** `sase final prepare MANIFEST` (`-j/--json`) observes opened repos, seals the intent, and prints an immutable ref. `sase monitor start -f/--completion REF` binds that ref atomically; a spawn failure unbinds it. Request fingerprints now include completion, profile, and policy.

**Verified**
- `cargo test -p sase_core continuation::completion` — 9 passed
- `cargo clippy -p sase_core -- -D warnings` — clean
- pytest on prepare/bind/parser suites — 55 passed, including no `final_submission.json` on prepare and rollback after a failed start
- `sase bead epic-symbols sase-zl.8` — no leftovers

**Not green on `just check`:** pre-existing mypy in `continuation_budget.py` (noted as a follow-up), feature-flag bead `sase-z9`, symvision private imports, and toobig on `continuation_capture.py`. Host consumption of a sealed success intent remains **sase-zl.9**.
