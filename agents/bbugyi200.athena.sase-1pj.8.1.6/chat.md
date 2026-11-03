# Chat History - ace-run (sase-1pj.8.1.6)

- **TIMESTAMP:** 2026-11-02 22:17:53 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1pj.8.1.6

## Prompt

#gh:gh_sase-org__sase
%id(6, clan=sase-1pj.8.1, bead=sase-1pj.8.1.6)
%model:@medium
%auto
%w(sase-1pj.8.1.5, for_epic=false)
%w(bead=sase-1pj.8.1.5)
Can you complete the work for bead sase-1pj.8.1.6? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1pj.8.1.6` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything, and run `sase bead open sase-1pj.8.1.6` only if the work
is genuinely unfinished. Read its
description and design file with `sase bead read sase-1pj.8.1.6 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1pj.8.1.6 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1pj.8.1.6`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1pj.8.1.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Bead `sase-1pj.8.1.6` (readout-adapter) is done and closed.

What landed:
- New thin adapter [src/sase/core/instruction_readout.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/core/instruction_readout.py) over the Rust `classify_instruction_readout` binding — no Python fallback, errors surfaced as a private contract error per the `instruction_manifest` sibling convention.
- [src/sase/instructions/readout.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/instructions/readout.py) now gathers staged records/receipts, `handoff_protocol`, lifecycle facts, accepted/not-required declaration evidence, prepared-intent evidence, and a bounded legacy tail scan — and delegates all class precedence to the Rust core. Held staged handoffs with a missing required declaration score `miss` even without an adopted lifecycle entry; legacy `killed`/unspecified evidence keeps its archived class. Tail markers reduced to real `propose` invocations (validate/decide/help no longer count).
- Pin ratcheted `65925ca8` → `6cd64a9c` (the readout-core commit); `.venv` rebuilt so the new binding imports.
- [tests/instructions/test_readout.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/instructions/test_readout.py): 12 new tests (staged miss/keep-class, prepared-intent contract, legacy-killed preservation, validate/help exclusion, adapter matrix + rejection); two old accepted-beats-handoff expectations updated to the new handoff-wins precedence.
- Docs inventory bullet in `docs/contribute/rust-backend.md`.

Verification: readout suite 32/32, full `tests/instructions/` 212 green, related handler/verify/monitor/finalizer suites green, and every `just check` lint gate green (ruff, mypy, symvision after privatizing the error, feature-flags, docs). The full scoped test lane stalled on host contention (load1 >25 for ~30 min), so I stopped my run and closed on the green gates plus the fully-covered change surface — noted on the bead.

Declaration accepted for bead `sase-1pj.8.1.6` (commit, close).
