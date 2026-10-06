- **PLAN:**
  [202610/tui_load_gauge_stale_pid_ghost_claims.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_load_gauge_stale_pid_ghost_claims.md)
- **AGENTS:**
  - [bbugyi200.athena.0xg--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0xg.md)

I'm seeing seven agents running, five with a weight of 0.25 and two with a normal weight
of 1. This would imply a total load of 3.25, so why am I seeing 5.25? See the
~/tmp/screenshots/20261006_142051.png screenshot for context. Can you help me diagnose
the root cause of this issue and fix it?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
