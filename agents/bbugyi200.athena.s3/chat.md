# Chat History - ace-run (s3--plan)

- **TIMESTAMP:** 2026-08-02 11:49:06 EDT
- **MODEL:** claude/opus
- **AGENT:** s3--plan

**Plan:** /home/bryan/.sase/plans/202608/xprompt_show.md


## Prompt

#gh:gh_sase-org__sase Can you help me add a new `sase xprompt show` command that displays an xprompt definition (including any properties defined for that xprompt) using excellent xprompt syntax highlighting (see the syntax highlighting we use in the prompt input widget for inspiration)? I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/xprompt_show.md`

> # Plan: `sase xprompt show`
> ## Goal
> Give SASE a first-class, human-facing way to read one xprompt definition. `sase xprompt list` already emits the whole
> catalog as JSON and `sase xprompt catalog` renders a PDF, but there is no way to ask "what exactly is `#sase/reads`,
> what properties does it declare, and what does its body look like?" without finding the file by hand. `show` answers
> that in one command, and it renders the body with real xprompt syntax highlighting rather than generic markdown —
> invocations, directives, segment separators, skill references, Jinja, placeholders, and artifact references all get the
> same colors the ACE prompt input bar gives them.
> Three qualities drive every decision below:
> - **Intuitive** — one required positional, three flags, and a name field that accepts whatever the user has in their

*See full plan file for details.*

