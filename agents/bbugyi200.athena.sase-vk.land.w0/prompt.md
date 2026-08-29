#gh:gh_sase-org__sase Can you help me add support to memory webs for inline and explicit memory file
links?

- For example, the glossary memory web in this project already uses an "inline" link
  reference strategy and should be configured as such explicitly (add a new config field
  that is supported by memory web files that enables this).
- All memory files should support explicit `[[foobar]]` links in reference memories and
  memory strands! For example, the sase/memory/decisions/gates-never-block.md file
  contains `[[decisions/single-turn-agents]]`, so the
  sase/memory/decisions/single-turn-agents.md memory strand should be rendered at the
  bottom of the output of the `sase memory show decisions:gates-never-block.md`
  command's output (just like we do for `sase memory read glossary:*` commands already).
- Update the /sase_memory_write xprompt skill to make agents aware of this new
  functionality and use it by linking to related memory files appropriately.
- Make sure existing memory strands link to related strands appropriately now. For
  example, do all auto-generated task type memory strands link to the task types they
  are related to appropriately?

#plan #m_opus %w:sase-vk.land