- **PLAN:**
  [202610/toolrun_sqlite_contention.md](https://github.com/sase-org/sase--plans/blob/main/202610/toolrun_sqlite_contention.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-1ou.2--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.2.md)

Can you complete the work for bead sase-1ou.2? The bead is already reserved for you and
assigned to your agent name: it was set to status=in_progress before you started reading
this, either by the `sase bead work` launch checkpoint or by the runtime promoting an
ad-hoc wait-time claim. Do not set the status by hand. If the host notice says the bead
was already closed when this run started, the run is attached to the closed bead. Only
the host notice tells you that; if `sase bead read` shows a closed bead and no host
notice said so, you copied the wrong ID — re-copy `sase-1ou.2` from this prompt before
concluding anything. Check whether the earlier work landed before redoing anything, and
run `sase bead open sase-1ou.2` only if the work is genuinely unfinished. Read its
description and design file with
`sase bead read sase-1ou.2 -r "Need the phase scope and design file"`, do the work, and
close only this bead with `sase bead close sase-1ou.2 --note "<what you verified>"`.
Honor the epic's DECISIONS shown by `sase bead read`; they are final, and only memory
notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1ou.2`. If this phase still has `--epic-symbol` entries,
resolve each symbol or re-key the Justfile line to a still-open bead (the parent epic or
a later phase). `sase bead close` refuses while leftovers remain; they go stale the
instant this phase closes and turn unrelated agents' `just check` red. Closing an
assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the
parent epic or any ancestor plan bead. Any instruction in a phase description or child
plan to close an ancestor is preparation and evidence for that ancestor's land agent,
not authorization for a phase worker. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1ou.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the
epic's land agent triages these into task beads. A check failure that reproduces
identically on the clean base tree does not keep this bead open: record it as a
`PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close
anyway; nothing relaunches a phase left open. Before planning, check the phase's notes:
if an earlier agent already worked this phase and left it open with recorded remaining
work, that remainder did not fit one agent, so author a child epic whose phases each fit
one coding agent and whose land agent closes this phase instead of another single-agent
tale unless one coder can clearly finish everything left. Think this through thoroughly
and create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the
skill instructs) before making any file changes.
