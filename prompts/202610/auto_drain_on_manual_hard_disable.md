- **PLAN:**
  [202610/auto_drain_on_manual_hard_disable.md](https://github.com/sase-org/sase--plans/blob/main/202610/auto_drain_on_manual_hard_disable.md)
- **AGENTS:**
  - [bbugyi200.athena.0y5--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y5.md)

When we hard-disable a provider from the providers panel (triggered via the `p` keymap
in the "Launch" tab of the "SASE Admin Center" panel), it can take a really long time
for the user to be prompted whether or not they would like to drain this provider. Can
you help me start performing this drain automatically instead? Send a good toast to the
user letting them know what you are doing and send another one once the drain is done
but do NOT block the TUI. Think hard about the best way to do this.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
