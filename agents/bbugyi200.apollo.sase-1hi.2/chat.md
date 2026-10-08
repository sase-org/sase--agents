# Chat History - ace-run (sase-1hi.2)

- **TIMESTAMP:** 2026-10-07 19:33:04 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1hi.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-1hi, bead=sase-1hi.2)
%model:@medium
%auto
Can you complete the work for bead sase-1hi.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-1hi.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1hi.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-1hi.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1hi.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open.

## Response

Bead sase-1hi.2 is done and closed.

**What landed** (11 files edited, 4 created):

- **Launch provenance** — every agent's `agent_meta.json` now records `prompt_origin` (`typed`/`generated`/`unknown`) and `prompt_source_surface`. New [launch_provenance.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/agent/launch_provenance.py) reuses the existing history classification (`effective_prompt_origin`), so history and metadata can never disagree. Stamps travel via child env: classifying funnels stamp explicitly (CWD launcher incl. `sase run` surface, bead-work adapter as generated), `spawn_agent_subprocess` fills gaps fail-closed (valid ambient stamp inherited, else generated), the runner persists it, and it survives directive-extraction rewrites. Follow-ups and axe helper runners record generated.
- **Gate `caller`** — `execute_gate_selection` writes `caller: human|agent` on every `response.json`, classified from the submitting process via `current_actor()`, failing closed to agent. The self-reported `source` field is untouched.
- **Gatherer** — new [plan_human_text.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/sdd/plan_human_text.py) returns only human-written text: root `submitted_prompt.md` when root origin is typed (prev-chain walk plus session-parent fallback), feedback bullets from human-caller/non-auto responses, and Q&A `custom_feedback`/`global_note` under the same rule. Selected option labels never count; missing/legacy records yield nothing.

**Verification:** 24 new tests pass; one existing bead-work test updated to the new stamp contract. `sase tool run check` passes all lint gates except a symvision private-import failure that reproduces identically on the clean base tree (verified via stash) — recorded as a follow-up, bead closed anyway per instructions. All other existing-suite failures match the base tree exactly (environmental stale core wire). `epic-symbols` is clean. Two `PROPOSED FOLLOW-UP` notes recorded (pre-existing symvision failure; multi-round question-bundle reachability).

Declaration submitted: commit with bead_action close for sase-1hi.2.
