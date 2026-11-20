# Chat History - ace-run (sase-1uj.1)

- **TIMESTAMP:** 2026-11-20 17:46:54 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1uj.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-1uj.1, bead=sase-1uj.1)
%clan(sase-1uj, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-1uj.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1uj.1` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1uj.1` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1uj.1 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1uj.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1uj.1 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1uj.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1uj.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Bead `sase-1uj.1` is done and closed.

What landed (15 files, `hydrogen_advisory = yes` and `image_pool = yes` branches per the epic's decisions):

- [models.yml](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/src/sase/llm_provider/models.yml) — four `gemini-4-neon-*` slugs leading the agy family, `neon4x/neon4h/neon4m/neon4l` aliases, info advisories per Neon slug (`needs Google AI Pro or Ultra`), and per-Hydrogen advisories (`needs paid Google AI Pro or Ultra`); comment block no longer claims Hydrogen is on every plan.
- [_agent_list_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/src/sase/ace/tui/widgets/_agent_list_helpers.py) — `"neon"` short name before `"argon"`.
- Docs — new Neon paragraph and corrected Hydrogen gating in [agy.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/docs/reference/providers/agy.md), "Neon, Argon, and Hydrogen entitlement advisories" in [models.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/docs/reference/providers/models.md), plus `just fix`-regenerated model tables.
- Tests — Neon entries in the agy core/probe/indicator/picker tests, new `test_agy_flags_neon_as_pro_gated` and `test_agy_flags_hydrogen_as_paid_pro_gated` replacing the no-advisory Hydrogen test, a neon TUI test, and updated jump targets; 139 passed.
- PNG goldens — 2 updated (`28 models` count and the `gemini-4-neon-xhigh` effort row, both visually inspected); update status `applied`, 0 stale.

Verification: `just fix` clean; `sase tool run check` passed every lint and docs gate. Its scoped test lane ended 4 failed + 4 errors, but I re-ran each on the stashed clean base and all reproduce identically (completion-snapshot drift on `artifact link list`, real-gateway errors, one KNOWN audit failure, one FLAKY budget test) — recorded as two `PROPOSED FOLLOW-UP` notes, no `--epic-symbol` leftovers.

Declaration accepted; commit staged for the 15 finished paths under bead `sase-1uj.1`.
