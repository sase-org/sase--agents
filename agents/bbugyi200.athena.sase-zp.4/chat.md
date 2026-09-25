# Chat History - ace-run (sase-zp.4)

- **TIMESTAMP:** 2026-09-11 19:31:52 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-zp.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-zp, bead=sase-zp.4)
%model:@small
%auto
%w:sase-zp.3
%w(bead=sase-zp.3)
Can you complete the work for bead sase-zp.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-zp.4 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-zp.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-zp.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design file, and the SASE skills I need so I can complete `sase-zp.4` without touching the parent epic.

Next I’ll load the bead details, patches skill, and project context so the work matches the assigned design.

The bead is a docs/integration phase. I’ll read the design file and parent epic next so the documentation matches the shipped workflow.

The design is clear: docs, memory, skill source, and one integration test. I’ll inspect prior phases and the current docs/code so the updates match the shipped contract.

I’ll read the docs, memory, and existing capacity tests next so the updates match the contract instead of rewriting from scratch.

I have the contract and the stale docs. Next I’ll update the docs, memory, and skill source, then add the gate-to-admission integration test.

`extract_prompt_directives` does not expand `#bd/land_epic`, so the integration test will expand xprompts first. I’m applying the documentation updates now.

The remaining `runners=` mentions are migration notes and extra-wait rejections. Next I’ll add the gate-to-admission integration test.

`just fmt` is waiting on a Cargo build lock. I’ll check which process holds it so we aren’t stuck behind an unrelated rebuild.

The core rebuild is still compiling. I’ll format just the files I changed so we aren’t blocked on that lock.

Scoped tests escalated to the full suite after the core rebuild and then queued. I’ll stop that run and execute the focused capacity tests instead.

Closed **sase-zp.4**. Capacity is now documented and checked from epic approval through weighted admission.

**Docs and memory**
- `docs/beads.md`: `-c/--capacity` and `-C/--cl-name`, multi-target examples, epic Custom Approval Capacity control
- `docs/xprompt.md`: `capacity=` grammar, completion, examples, pre-admission vs global budget, `runners=` migration
- Related docs updated the same way: ACE, axe, CLI, configuration, editor, runner-slots troubleshooting
- `sase/memory/xprompts.md` rewritten in place, then `sase memory init`
- Skill source `src/sase/xprompts/skills/sase_agents_status.md` updated; generated skill copies were not deployed from this dirty checkout

**Integration test** (`tests/test_capacity_gate_to_admission.py`)
- Gate `capacity=1` → launch argv → bead-work render → xprompt expansion → Rust extraction → weighted admission
- Phase and land capacity match; land weight stays `2.0`
- Four `0.25` claims satisfy capacity `1`; one weight-`2` claim does not
- Omitted-capacity path keeps no `%queue(capacity=)` line, still authors land weight `2.0`, and still honors the global budget

**Verification**
- Focused pytest: 71 passed
- `git diff --check` clean; `just fmt` clean
- `just check`: fmt/ruff/mypy/feature-flags passed; stopped on pre-existing symvision private imports already tracked by ready task **sase-zk**
- `sase bead epic-symbols sase-zp.4`: no leftovers

Did not close the parent epic **sase-zp**.
