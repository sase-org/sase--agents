#gh:gh_sase-org__sase The `just test` command just failed (see the output below). Can you help me diagnose the root cause of this issue and fix it? #plan
```
============================================================================= short test summary info ==============================================================================
FAILED tests/ace/tui/widgets/test_prompt_xprompt_highlight.py::test_xprompt_highlight_overlay_marks_spans_and_registers_styles - AssertionError: assert 'xprompt.skill' in ['heading', 'xprompt.invocation', 'xprompt.invocation_arg', 'xprompt.directive', 'xprompt.invocation', 'xprompt.invocation_arg', ...]
======================================================= 1 failed, 17213 passed, 7 skipped, 46 warnings in 138.84s (0:02:18) ========================================================
error: recipe `test` failed on line 212 with exit code 1
```