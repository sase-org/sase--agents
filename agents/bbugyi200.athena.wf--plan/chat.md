# Chat History - ace-run (wf--plan)

- **TIMESTAMP:** 2026-08-09 09:06:13 EDT
- **MODEL:** claude/opus
- **AGENT:** wf--plan

**Plan:** /home/bryan/.sase/plans/202608/glossary_highlight_flicker.md


## Prompt

#gh:gh_sase-org__sase The syntax highlighting for glossary terms in the prompt input widget flickers everytime a character is typed, which is distracting and annoying. Can you help me diagnose the root cause of this issue and fix it? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/glossary_highlight_flicker.md`

> # Plan: Stop glossary highlight flicker in the prompt input widget
> ## Problem
> Glossary term styling (bold theme-accent + underline) in the ACE prompt input widget
> blinks off and back on with every character typed.
> ## Root cause
> `PromptGlossaryMixin._build_highlight_map()` drops the entire glossary overlay on the
> highlight rebuild that immediately follows every edit, because its warm-catalog lookup
> is gated on a text-equality check that is guaranteed to be stale at that moment.
> `src/sase/ace/tui/widgets/_prompt_glossary.py:176-183`:
> ```python

*See full plan file for details.*

