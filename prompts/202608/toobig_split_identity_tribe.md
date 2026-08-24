- **PLAN:**
  [202608/toobig_split_identity_tribe.md](https://github.com/sase-org/sase--plans/blob/main/202608/toobig_split_identity_tribe.md)
- **AGENTS:**
  - [bbugyi200.athena.0c6--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0c6.md)

Yesterday, I made some improvements to the `toobig_split` chop. Namely, we were supposed
to start using a name like `toobig-3j.<basename>.0` (using the special `{@<id>}` syntax
that should be supported in sase agent names). I'm not sure that change was ever applied
however. Moreover I'm seeing the agents created by this chop are no longer being added
to the `@chop` tribe (see #sshot for context). Can you help me diagnose the root cause
of this issue and fix it?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
