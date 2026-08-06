- **PLAN:**
  [202608/bead_close_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_close_history.md)
- **AGENTS:**
  - [bbugyi200.athena.tr--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.tr.md)

currently if a closed bead appears to be a duplicate of an unrelated issue that a sase agent detects, then that agent
+1s the closed task, which reopens it. This is fine but the problem is that I think we lose the reason that gets left by
the agent that closed the bead. Also it's not clear that a particular +1 reopened the bead from the output of the
`sase bead show` command. Can you help me fix these issues?

I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but
not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author
the appropriate tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill
instructs) before making any file changes.
