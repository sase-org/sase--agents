%wait(sase-vk.land.w2)
#gh:gh_sase-org__sase Can you help me add support for new frontmatter fields to memory files which
enable us to specify the link rendering/reference strategy used by that memory file when
read using the `sase memory show/read` commands?

- The link rendering strategy controls how the linked memory is rendered at the bottom.
- The link reference strategy controls how we detect links to other memory files from
  the current memory file's contents.
- Memory webs should be able to be configured with these fields so all strands don't
  need to set them.
- For example, the glossary memory web in this project already uses an "implicit" link
  reference strategy and an "inline" rendering strategy (i.e. the contents of the
  referenced files are rendered at the bottom of the `sase memory show` command's
  output) and should be configured as such explicitly.
- Memory files should have a default link reference strategy of "explicit" and a default
  rendering strategy of "reference", which means that `[[foobar]]` link references
  should be detected by default in reference memories and memory webs and should result
  in a new "Linked References" section at the bottom of the `sase memory show` command's
  output that contains a list of numbered sub-sections dedicated to each linked
  reference (see how we do this for reference memory in agent instruction files for
  inspiration).
- An explicit link reference should be able to specify that it should be rendered inline
  (regardless of the configured rendering strategy for that memory file) by prefixing
  the link with `!` (ex: `![[foobar]]`).
- For example, the sase/memory/decisions/gates-never-block.md file contains
  `![[decisions/single-turn-agents]]`, so the
  sase/memory/decisions/single-turn-agents.md memory strand should be rendered at the
  bottom of the output of the `sase memory show decisions:gates-never-block.md`
  command's output (just like we do for `sase memory read glossary:*` commands already).
- Update the /sase_memory_write xprompt skill to make agents aware of this new
  functionality and use it by linking to related memory files appropriately.
- Make sure existing memory strands link to related strands appropriately now. For
  example, do all auto-generated task type memory strands link to the task types they
  are related to appropriately?

#plan #m_opus 