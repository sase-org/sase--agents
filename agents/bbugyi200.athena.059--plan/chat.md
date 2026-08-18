# Chat History - ace-run (059--plan)

- **TIMESTAMP:** 2026-08-17 18:08:58 EDT
- **MODEL:** claude/opus
- **AGENT:** 059--plan

**Plan:** /home/bryan/.sase/plans/202608/prompt_repo_mentions.md


## Prompt

#gh:gh_sase-org__sase Can you help me start highlighting and underlining linked repos ("sase-core"
for this repo, for example) when found in the prompt input widget just like we do with
glossary terms already (but use a distinct color)?

- Also let's add support to the `K` / `<ctrl+]>` keymaps for linked repos.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/prompt_repo_mentions.md`

> # Plan: Repo mentions in the prompt
> ## Goal
> A repo name is one of the most load-bearing tokens a SASE prompt can contain, and today
> it is dead text. After this epic, writing `sase-core` in a prompt input lights it up the
> same way `Agent Hood` does — bold, underlined, and clearly a thing you can act on — but
> in its own color, and with `K` and `Ctrl+]` bound to the two questions you actually have
> about a repo: _what is it?_ and _take me there_.
> The existing project-glossary overlay (`src/sase/ace/tui/widgets/_prompt_glossary.py`,
> `src/sase/xprompt/glossary_catalog.py`,
> `src/sase/ace/tui/actions/_startup_prompt_catalog.py`) is the template. This epic builds

*See full plan file for details.*

