- **PLAN:**
  [202608/agent_prompt_wrap_width_120.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_prompt_wrap_width_120.md)
- **AGENTS:**
  - [bbugyi200.athena.ua--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.ua.md)

I think we use a different column character count (i.e. width) with `prettier` when preparing a prompt for a launched
agent vs when using the `gf` / `<ctrl+g>f` keymaps from the prompt input widget. Can you help me fix this by using the
longer width (I think the prompt input widget keymaps currently use the shorter width, so it should be changed to match
the width used automatically when preparing sase agent prompts)? Think this through thoroughly and create a plan using
your `/sase_plan` skill. Choose and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
