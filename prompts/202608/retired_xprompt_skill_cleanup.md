- **PLAN:**
  [202608/retired_xprompt_skill_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/202608/retired_xprompt_skill_cleanup.md)
- **AGENTS:**
  - [bbugyi200.athena.098--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.098.md)

When we've deleted or renamed xprompt skills in the past, these get added to my chezmoi
repo and chezmoi gets applied, but we don't seem to remove the old skill files. For
example, isn't the /sase_artifacts_file skill supposed to be gone (I just watched a sase
agent use it)? Moreover, even if we did, chezmoi does not automatically delete the
target locations for deleted or renamed files. Can you help me fix this?

- Let's start tracking which files in the user's chezmoi repo are managed by sase (make
  sure any existing xprompt skills are tracked too--not just new xprompt skills).
- This way we can start deleting the corresponding files when we rename /delete xprompt
  skills.
- When sase applies xprompt skill changes to chezmoi and skill files need to be deleted,
  we need to make sure to delete the versions in my chezmoi repo and the target/real
  versions of those files.
- Make sure any UI surfaces that prompt the user about chezmoi changes include some
  information about the files that will be deleted.
- Finally, find and delete any old `/sase_*` skills that are configured for agent CLI
  providers on this machine.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
