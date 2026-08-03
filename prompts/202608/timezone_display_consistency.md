- **PLAN:**
  [202608/timezone_display_consistency.md](https://github.com/sase-org/sase--plans/blob/main/202608/timezone_display_consistency.md)
- **AGENTS:**
  - [bbugyi200.athena.sn--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sn.md#member-plan)

There seem to be many cases in sase where we display timestamps to the user that reflect UTC time instead of the
timezone specified by the `timezone` sase config field. Can you help me track down all instances of this bad behavior
and fix them? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the
appropriate tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill
instructs) before making any file changes.
