- **PLAN:**
  [202608/agent_family_completion_previews.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_family_completion_previews.md)
- **AGENTS:**
  - [bbugyi200.athena.03u--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03u.md)

The completion for agent family names in the prompt input widget and external editors
(via LSP support) does not show a great preview at the moment (see #sshot for an example
of this completion menu). Can you help me fix this?

- Let's start using the title of the tale/epic in the preview when available.
- Make sure you indicate whether the plan is an epic or a tale and, for epics, provide
  some concise but useful information about the phases associated with that epic.
- If that's not available then start showing a snippet of the prompt that the user used
  for the initial agent (instead of the names of the family's members, like we do now).
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
