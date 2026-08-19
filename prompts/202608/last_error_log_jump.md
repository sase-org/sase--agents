- **PLAN:**
  [202608/last_error_log_jump.md](https://github.com/sase-org/sase--plans/blob/main/202608/last_error_log_jump.md)
- **AGENTS:**
  - [bbugyi200.athena.07n--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07n.md)

Sometimes sase agent launches fail and then I receive a toast telling me to go the
"Logs" tab of the "SASE Admin Center" panel to find the error messaage. The problem is
that this logs tab has many sources and navigating it to find a specific error is
difficult. Can you help me fix this by adding a new `,L` keymap that jumps directly to
the specific log entry related to the most recently registered error ("registered
errors" should always be associated with toasts that direct the user to use the `,L`
keymap) on that tab?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
