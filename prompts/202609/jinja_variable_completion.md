- **PLAN:**
  [202609/jinja_variable_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/jinja_variable_completion.md)
- **AGENTS:**
  - [bbugyi200.apollo.3g--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3g.md)

Can you help me add excellent jinja2 variable completion support to the prompt input
widget and external editors (via LSP support)?

- This completion menu should show all valid jinja2 variables that can be used after
  `{{` is typed.
- This includes, for example, any xprompt properties that are defined for the current
  xprompt / prompt input widget stack and any builtin jinja2 variables that sase injects
  / makes available to all sase agent prompts.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
