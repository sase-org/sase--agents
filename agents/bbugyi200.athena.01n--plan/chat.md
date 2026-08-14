# Chat History - ace-run (01n--plan)

- **TIMESTAMP:** 2026-08-14 13:56:05 EDT
- **MODEL:** claude/opus
- **AGENT:** 01n--plan

**Plan:** /home/bryan/.sase/plans/202608/xprompt_spacer_tabstop_jump.md


## Prompt

#gh:gh_sase-org__sase In the prompt input widget, if an xprompt is completed that doesn't have any
args or that has only one optional arg, we insert a space after the xprompt when the
user accepts the completion (e.g. hits `<enter>`). If the user is in the middle of a
sase snippet, this space is often manually deleted by the user before they press `<tab>`
again to travel to the next tabstop. Can you help me make it so this space is deleted
automatically in that case (when the user completes an xprompt and then immediately uses
`<tab>` to jump to the next snippet tabstop)? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/xprompt_spacer_tabstop_jump.md`

> # Plan: Drop the xprompt completion spacer when Tab jumps to the next tabstop
> ## Problem
> Xprompts with no required inputs complete to `#name ` — with a deliberate trailing
> spacer — from all three acceptance paths (`Ctrl+T` panel accept / `<enter>`, `Ctrl+L`
> soft completion, and the `#@` selector). That spacer is right when the user keeps typing
> prose, but wrong when the accepted reference sits at a snippet tabstop and the user's
> next keystroke is `Tab` to travel to the next tabstop: the reference is finished, the
> surrounding template already supplies its own separators, and the spacer becomes a stray
> space the user deletes by hand before pressing `Tab`.
> Concrete repro (snippet template `Use $1 to fix $2.`):

*See full plan file for details.*

