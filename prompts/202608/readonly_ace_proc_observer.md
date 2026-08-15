- **PLAN:**
  [202608/readonly_ace_proc_observer.md](https://github.com/sase-org/sase--plans/blob/main/202608/readonly_ace_proc_observer.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-m9.3.1.4--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.3.1.4.md)

Can you complete the work for bead sase-m9.3.1.4? The bead is already reserved for you
and assigned to your agent name: it was set to status=in_progress before you started
reading this, either by the `sase bead work` launch checkpoint or by the runtime
promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its description
and design file, do the work, and close only this bead with
`sase bead close sase-m9.3.1.4 --note "<what you verified>"`. Closing an assigned phase
bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or
any ancestor plan bead. Any instruction in a phase description or child plan to close an
ancestor is preparation and evidence for that ancestor's land agent, not authorization
for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-m9.3.1.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the
epic's land agent triages these into task beads. Think this through thoroughly and
create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the
skill instructs) before making any file changes.
