- **PLAN:**
  [202609/quit_confirm_inflight_work.md](https://github.com/sase-org/sase--plans/blob/main/202609/quit_confirm_inflight_work.md)
- **AGENTS:**
  - [bbugyi200.apollo.2o--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2o.md)

I seem to be allowed to quit the TUI (i.e. using the `q` or `Q` keymaps) even when there
is a proc that is specific to the current TUI instance running without a y/n prompt to
the user (to confirm they really want to do this). This just caused me to only partially
kill an agent clan (`toobig-68`) on my Athena machine I think. Can you help me
confirm/deny my suspicion and fix the issue (i.e. add a y/n prompt and clean up the
athena machine if necessary)?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
