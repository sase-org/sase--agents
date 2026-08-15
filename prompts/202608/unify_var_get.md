- **PLAN:**
  [202608/unify_var_get.md](https://github.com/sase-org/sase--plans/blob/main/202608/unify_var_get.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-mg.land.w1--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-mg.land.w1.md)
- **ARTIFACTS:**
  - [README.md](https://github.com/sase-org/sase--beads/blob/main/pages/sase-mg/README.md)

Can you help me merge the current functionality of the `sase var show` command into the
`sase var get` command by having it accept an argument of the form `<agent_name>`? See
[@bead:sase-mg][1] for context. Also, let's update the /sase_var xprompt skill to give
agents excellent (but concise--remember that every token we add to context either helps
or hurts us) instructions on how they can use the `get|list|set` sub-commands of the
`sase var` command.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-mg/README.md
