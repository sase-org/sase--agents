- **PLAN:**
  [202608/agent_show_positional.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_show_positional.md)
- **AGENTS:**
  - [bbugyi200.athena.01t--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01t.md)

The `sase agent show` command accepts a required `-n|--name` option. Can you help me
make this a positional argument instead? Also, CLI options should never be required;
that's what positional arguments are for. Can you add similar guidance to the
sase/memory/cli_rules.md memory file?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
