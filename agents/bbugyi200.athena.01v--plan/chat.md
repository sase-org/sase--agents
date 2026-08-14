# Chat History - ace-run (01v--plan)

- **TIMESTAMP:** 2026-08-14 18:04:49 EDT
- **MODEL:** claude/opus
- **AGENT:** 01v--plan

**Plan:** /home/bryan/.sase/plans/202608/k_preview_shorthand_arg_text.md


## Prompt

#gh:gh_sase-org__sase Can you help me make the `K` keymap in the prompt input widget stop showing the preview for an xprompt when one of the `#foo: Some single-line arg...` or `#foo:: Some multi-line arg...` argument forms are used and part of the single/multi-line argument is selected (we should prefer all other functionalities of the `K` keymap before defaulting to this behavior)? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/k_preview_shorthand_arg_text.md`

> # `K` should stop previewing the owning xprompt from inside `#name: ` / `#name:: ` argument text
> ## Problem
> In prompt NORMAL mode, `K` (`_preview_token_under_cursor`) resolves what is under the
> cursor through `detect_preview_target_at_cursor()` in
> `src/sase/ace/tui/widgets/_prompt_preview_target.py`. That detector walks
> `iter_xprompt_references(text)` and returns the first reference whose
> `ref.start <= offset < ref.end`.
> For the shorthand argument forms, `ref.end` is not the end of the reference head — it is
> the end of the _argument text_:
> - `#name: text` (single colon + space) runs to the next blank line

*See full plan file for details.*

