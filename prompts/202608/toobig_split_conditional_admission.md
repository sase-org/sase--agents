- **PLAN:**
  [202608/toobig_split_conditional_admission.md](https://github.com/sase-org/sase--plans/blob/main/202608/toobig_split_conditional_admission.md)
- **AGENTS:**
  - [bbugyi200.athena.0c1--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0c1.md)

Yesterday, we fixed the `toobig_split` chop's duplicate handling by checking the HEAD
commit. This was a hacky, bad solution. Can you help me get rid of this solution in
favor of using the new `%if` directive for this (see the sase-s6 epic bead for context)?
This directive should accept a code block that ensures that the file is still >=700
lines long.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
