# Chat History - ace-run (ws--plan)

- **TIMESTAMP:** 2026-08-09 15:53:16 EDT
- **MODEL:** claude/opus
- **AGENT:** ws--plan

**Plan:** /home/bryan/.sase/plans/202608/glossary_line_break_matching.md


## Prompt

#gh:gh_sase-org__sase It looks like glossary terms are not recognized when split across lines (see "xprompt memory" in #sshot for an example). Can you help me fix this? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/glossary_line_break_matching.md`

> # Recognize glossary terms that wrap across a line break
> ## Problem
> A hard-wrapped ACE prompt splits a multiword glossary term across two buffer lines, and
> the term stops being recognized. In the reported case the prompt text is
> ```text
> - Let's start describing all sase sizes in a new sase/memory/sase_sizes.md xprompt
>   memory file that gets created automatically by the `sase memory init` command.
> ```
> `xprompt memory` is the configured term `Xprompt Memory`, but only the bare word
> `xprompt` is underlined: the shorter `Xprompt` entry wins because the longer phrase

*See full plan file for details.*

