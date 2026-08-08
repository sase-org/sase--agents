- **PLAN:**
  [202608/xprompt_skill_singular_namespace.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_skill_singular_namespace.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-hf.land.w2--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-hf.land.w2.md)

Can you now help me make it so xprompt skills are invoked using the `#skill/` prefix
instead of the `#skills/` prefix? Also, we made it a requirement that xprompt skills are
defined in sase/skills/ directories. This is correct but there should be one exception,
namely any builtin xprompt skills should be defined in the src/sase/xprompts/skills/
directory, not the src/sase/skills/ directory. Think this through thoroughly and create
a plan using your `/sase_plan` skill. Choose and author the appropriate tier, validate
and revalidate until it passes, then submit it with `sase plan propose` (as the skill
instructs) before making any file changes.
