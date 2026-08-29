#gh:gh_sase-org__sase Can you help me add a new `/sase_memory_write` xprompt skill?

- Sase agents should use this skill whenever they are instructed to or think it is a
  good idea to create a new or remove/modify an existing memory file.
- See the annotation tagged with `#a` that I left on an agent instruction file for more
  context on how agent instruction files should be modified. This annotation can be
  found in the ~/bob/ref/docs/sase_AGENTS_v3.md file.
- The skills, description, and contents should be excellent but concise. Remember that
  every token in context either helps or hurts us.
- Think hard about the instructions that this new skill contains, but it should at least
  meet the following requirements:
  - If an agent is about to create a plan that modifies memory files and the user's
    prompt did not explicitly request memory file changes then the agent should use its
    /sase_questions skill to confirm the memory edits are ok before planning.
  - If any other agent is attempting to modify memory files without explicit permission,
    via the user's prompt or an approved plan (I think we explicitly forbid memory file
    edit approvals in plans currently so make sure to modify agent instructions
    appropriately so we start allowing this), that agent should be instructed to create
    a new task bead with the memory task type using the /sase_new_task skill instead
    (they should NOT proceed with actually adding/editing/removing memory files).
  - These instructions should contain the following reminder: "Remember that every token
    in context either helps or hurts us."

#plan #m_opus