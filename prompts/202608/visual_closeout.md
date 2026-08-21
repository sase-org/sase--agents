- **PLAN:**
  [202608/visual_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/visual_closeout.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-rm.13--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rm.13.md)

Can you complete the work for bead sase-rm.13? The bead is already reserved for you and
assigned to your agent name: it was set to status=in_progress before you started reading
this, either by the `sase bead work` launch checkpoint or by the runtime promoting an
ad-hoc wait-time claim. Do not set the status by hand. Read its description and design
file, do the work, and close only this bead with
`sase bead close sase-rm.13 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-rm.13`. If this phase still has `--epic-symbol` entries,
resolve each symbol or re-key the Justfile line to a still-open bead (the parent epic or
a later phase). `sase bead close` refuses while leftovers remain; they go stale the
instant this phase closes and turn unrelated agents' `just check` red. Closing an
assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the
parent epic or any ancestor plan bead. Any instruction in a phase description or child
plan to close an ancestor is preparation and evidence for that ancestor's land agent,
not authorization for a phase worker. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-rm.13 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the
epic's land agent triages these into task beads. Think this through thoroughly and
create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the
skill instructs) before making any file changes.
