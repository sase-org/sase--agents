- **PLAN:**
  [202608/epic_resume_gate.md](https://github.com/sase-org/sase--plans/blob/main/202608/epic_resume_gate.md)
- **AGENTS:**
  - [bbugyi200.athena.05e--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05e.md)

When an agent fails that is working a phase of an epic fails, it is often for a
transient reason and the next agent will succeed. Also sometimes the agent actually
completed its work so we just need to get the epic rolling again. See #sshot for an
example of this. What I normally do to fix this is run the
`sase bead work <epic_bead_id> -Y` command. Can you help me start sending a sase gate
when this happens that offers the user a single option which runs that command, with
`<epic_bead_id>` replaced with the appropriate epic bead's ID?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
