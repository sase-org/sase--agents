- **PLAN:**
  [202608/stepwise_hidden_step_collapse.md](https://github.com/sase-org/sase--plans/blob/main/202608/stepwise_hidden_step_collapse.md)
- **AGENTS:**
  - [bbugyi200.athena.02l--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02l.md)

When an xprompt workflow has hidden steps, we can view them by selecting their agent
shell / agent family and using the `l` keymap twice (once to expand the agent shell /
agent family and once to show hidden steps). The user is supposed to then be able to use
the `H` keymap to reverse these operations (the first use should hide hidden steps and
the 2nd use should collapse the agent shell / agent family). In #sshot, for example, if
the user were to press `H`, I would expect the `02i` agent family to remain open but for
its hidden steps to disappear. But this doesn't work. The entire `02i` agent family is
just immediately collapsed. Can you help me fix this?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
