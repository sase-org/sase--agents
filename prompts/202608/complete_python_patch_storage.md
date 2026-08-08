- **PLAN:**
  [202608/complete_python_patch_storage.md](https://github.com/sase-org/sase--plans/blob/main/202608/complete_python_patch_storage.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-hn.2--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-hn.2.md)

Can you complete the work for bead sase-hn.2? The bead is already reserved for you and
assigned to your agent name: it was set to status=in_progress before you started reading
this, either by the `sase bead work` launch checkpoint or by the runtime promoting an
ad-hoc wait-time claim. Do not set the status by hand. Read its description and design
file, do the work, and close the bead with
`sase bead close sase-hn.2 --note "<what you verified>"`. Closing an assigned phase bead
is unaffected by the parent-close descendant guard. Do NOT close the parent epic. Do not
create beads yourself: record discovered follow-up work as a `PROPOSED FOLLOW-UP:` entry
via `sase bead note sase-hn.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the
epic's land agent triages these into task beads. Think this through thoroughly and
create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the
skill instructs) before making any file changes.
