#gh:gh_sase-org__sase Can you help me start requiring that all tale plan files be assigned a size via
the `size` frontmatter property? I would also like to improvement sase agent
understanding of phase/plan/bead sizes (referred to as "sase sizes" for the rest of this
prompt) in general.

- Let's start describing all sase sizes in a new sase/memory/sase_sizes.md long-term
  memory file that gets created automatically by the `sase memory init` command.
- This file should be the ONLY data source (i.e. the canonical source of truth) that
  sase agents rely on (or have access to) for instructions related to sase sizes. This
  means that we should factor out any relevant text that is currently output by the
  `sase plan validate` command (when the `--explain` option is used) to this memory file
  and reference the memory file (with instructions to use the /sase_memory_read xprompt
  skill to read it) from that output text instead.
- This memory file should have sase/memory/sase_beads.md as the value for its `parent`
  frontmatter field. This is the first long-term memory file where I have attempted to
  use any file but AGENTS.md as the `parent` value, so I'm not sure this is even
  supported. If not, make sure to add excellent (robust, resiliant, and reliable)
  support for having one long-term memory file use another as its `parent`. We should
  render these memory file names and descriptions in the `sase memory read` command's
  output when the parent memory is read (see how we render long-term memories in agent
  instruction files for inspiration).
- Make sure that all of the guidance in the "Sase Size Guidance" section below is
  included in this memory file (reword and omit as you see fit, but keep in mind that
  every token in context either helps or hurts us). Where this guidance conflicts with
  existing guidance (remember that existing guidance should be removed in favor of
  referencing this new memory file), preference the instructions in the section below.

#plan #m_opus

### Sase Size Guidance

- Tale plan files MUST use a `size` of either `xsmall`, `small`, or `medium` (validate
  this via the `sase plan validate` command as well).
- Creating a plan with the /sase_plan skill is an activity that is always associated
  (either implicitly or explicitly) with either a `large` or `xlarge` size, which is
  decided by the agent based on whether the plan file they create has a `tale` (large)
  or `epic` (xlarge) tier.
- When creating new task beads, agents should default to using the `large` size for the
  bead they create unless they are very confident that they have identified the precise
  root cause of an issue (use `xsmall`, `small`, or `medium` in this case--and make sure
  the issue is precisely described in the bead's description) or they are very certain
  that the feature/issue is large enough that it will require an epic plan (i.e.
  multiple agents) to address.

### Related Changes

- As a part of this change, we should be able to get rid of the "coder" model alias
  bucket in favor of using the model aliases in the "phase_worker" model alias bucket
  for coder agents based on the size of the plan the agent is working.
- Make sure that we append `#plan` to the prompt we use to launch sase agents that work
  task beads when those tasks have a size of `large` or `xlarge`, so they create a plan
  with the /sase_plan xprompt skill. I'm not sure if we are doing this already or not.