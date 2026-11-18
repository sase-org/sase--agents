# Chat History - ace-run (1dm--plan)

- **TIMESTAMP:** 2026-11-17 15:43:04 EST
- **MODEL:** claude/opus
- **AGENT:** 1dm--plan

**Plan:** /home/bryan/.sase/plans/202611/gate_fit_teardown_crash.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/gate_fit_teardown_crash.md`

> # Fix the gate modal fit-callback teardown crash
> ## Problem
> The ACE TUI on apollo crashed (the whole app exited) on 2026-11-17 with this traceback,
> logged to `~/.sase/logs/tui.log`:
> ```
> File ".../textual/screen.py", line 1272, in _invoke_and_clear_callbacks
>   await invoke(callback)
> ...
> File "src/sase/ace/tui/modals/gate_input_panel.py", line 167, in _fit_body_scroll
>   footer = self.query_one("#gate-input-footer", Static)

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase The TUI just crashed on the apollo machine. Is this something we can/should fix?
If so, use your /sase_plan skill to plan the appropriate changes. %m:@xlarge

## Response

Checking the TUI log on apollo for the crash traceback.

Found it: `NoMatches` for `#gate-input-footer` in `GateInputPanel._fit_body_scroll`. Now inspecting the code.

Apollo runs the same commit as this workspace (`efc66a420b`), so the bug is still present on master. Checking history and how Textual runs these callbacks.

I have what I need. Writing the plan.

The review scroll sits inside the container, so only the footer case is uncovered there. Making that part of the plan definite.

Yes, this should be fixed. It's a real bug on current `master`: a cosmetic layout callback in the gate input modal took down the whole TUI. I've proposed a small plan for it, which is waiting for your approval.

**What crashed.** At 20:33:51 on apollo, `~/.sase/logs/tui.log` logged:

```
gate_input_panel.py:167 in _fit_body_scroll
  footer = self.query_one("#gate-input-footer", Static)
textual.css.query.NoMatches: No nodes match '#gate-input-footer' on GateInputPanel()
```

Apollo's checkout is at `efc66a420b`, the same commit as master here.

**Why it happens.**
- `_fit_body_scroll` is a sizing callback that gets queued to run on the next screen refresh. It's queued on mount, on every resize, and by itself whenever the body height changes.
- Textual (the TUI framework) doesn't tie that queued callback to the panel's lifetime, so it can still run after the panel is dismissed. The panel also keeps reporting itself as mounted during that teardown.
- Teardown removes the panel's child widgets one at a time. For a moment the outer container still exists but the footer is already gone.
- The callback only checks that the container exists before looking up the body and footer, so in that window the footer lookup fails. Our app-level handler treats any uncaught exception as fatal, so the whole TUI exits.
- The crash came about 5 seconds after "Started 6 agent(s)", which fits a gate modal being submitted and closed just before.

`CustomGateModal._fit_compact_review_scroll` (`src/sase/ace/tui/modals/custom_gate_modal.py:216`) has the same flaw and can crash the same way, so the plan covers it too.

**The plan** (a single-agent plan, size small):
- In both callbacks, put all three widget lookups inside one `try` and return quietly on `NoMatches`. This replaces the container-only check. It catches only that error, so other bugs in these callbacks still show up.
- Add regression tests that set up the exact state that crashed: a mounted modal with its footer removed (plus the body for the gate input panel). The tests must fail on the old code before the fix goes in.
- No change to the rule that any uncaught exception kills the TUI, and no screenshot or memory changes.

Other queued refresh callbacks elsewhere in the TUI weren't checked, and they could have the same weakness. These two are the only ones I confirmed.

Unrelated to the crash: apollo's installed sase tool runs Textual 8.2.8, while the repo's dev dependencies pin 8.0.1.
