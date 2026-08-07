- **PLAN:**
  [202608/gate_stdin_broken_pipe.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_stdin_broken_pipe.md)
- **AGENTS:**
  - [bbugyi200.athena.v4--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.v4.md)

The `just test` command is failing with a single failing test (see the command output
below for context). Can you help me diagnose the root cause of this issue and fix it?
Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.

```
============================================================================= short test summary info ==============================================================================
FAILED tests/ace/tui/test_notification_custom_gate.py::test_tracked_executor_reports_terminal_and_extra_commands_live - AssertionError: assert False is True
======================================================= 1 failed, 27063 passed, 7 skipped, 69 warnings in 240.23s (0:04:00) ========================================================
```
