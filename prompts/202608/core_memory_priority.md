- **PLAN:**
  [202608/core_memory_priority.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_memory_priority.md)
- **AGENTS:**
  - [bbugyi200.athena.0cx--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0cx.md)

Can you help me add an optional `priority` field to "core" memory files (see the sase-sq
epic bead for context--leave notes on this bead / this bead's children if appropriate)
that specifies the order it is rendered in the "Tier 1" section in agent instruction
files?

- This field should have a default value of `20`.
- We should give the auto-generated (by the `sase init` command) sase/memory/sase.md
  memory file a priority of `10` so it is always the first sub-section of the "Tier 1"
  section (unless a user explicitly sets a lower priority using the `priority`
  frontmatter field in one of their core memory files).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
