- **PLAN:**
  [202608/family_shell_metadata.md](https://github.com/sase-org/sase--plans/blob/main/202608/family_shell_metadata.md)
- **AGENTS:**
  - [bbugyi200.athena.0aj--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0aj.md)

Can you help me migrate the `Model:` field in the agent metadata panel to `Shells:` when
an agent family is selected (we should continue to use `Model:` when an agent shell is
selected) since not every shell is associated with a model?

- Monitors (i.e. proc shells), for example, do not have a model associated with them.
- As part of this change let's stop showing the model for monitor shell entries of this
  `Shells:` field.
- Instead, let's display the command that was used for the monitor if it is short enough
  to display on one line. Otherwise (if the command is too long to show on one line), we
  should show the reason string that was provided to the `sase monitor` command. Make
  sure we wrap this reason string across multiple lines if it is too long in a visually
  appealing way.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
