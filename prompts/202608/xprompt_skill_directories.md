- **PLAN:**
  [202608/xprompt_skill_directories.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_skill_directories.md)
- **AGENTS:**
  - [bbugyi200.athena.vh--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.vh.md)

Can you help me start requiring that xprompt skills be defined in a sase/skills/
directory?

- Currently, these are defined in sase/xprompts/skills/ directories normally, but it is
  the `skill: true` frontmatter property that really controls whether an xprompt is an
  xprompt skill or not (I think at least--you should verify this).
- Also, let's start requiring that, in order to invoke these as xprompts (instead of as
  skills using the `/` prefix), that we include the `skills/` prefix (e.g. `#skills/foo`
  instead of `#foo`).
- Make sure you migrate all of my xprompt skills accordingly across all of my enabled
  sase projects and my chezmoi repo.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
