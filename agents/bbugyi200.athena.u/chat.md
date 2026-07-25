# Chat History - ace-run (u--plan)

- **TIMESTAMP:** 2026-07-06 19:33:02 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** u--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-u__plan-260706_192303.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260706_192303.md`

**Plan:** /home/bryan/.sase/plans/202607/tab_onboarding_quickstart.md


## Prompt

#gh:gh_sase-org__sase On the Agents tab and the PRs tab in the TUI, we currently show onboarding pages specific to those tabs when there's nothing else interesting to show. Can you help me make several big improvements to those pages?

- The content that we show there now should be preserved via the `,?` keymap that already exists and shows the contents for these pages in a pop-up panel.
- The new content will be very different. We'll start with a one to two sentence summary of what the tab is all about. Then we'll describe the five to seven most important global keymaps that the user Would most likely find value from if they don't know where to get started or if they are just getting started (i.e. configuring sase, installing plugins, etc...)
- The logic that decides when we show the onboarding page for the PRs tab is currently broken. What we should do instead is always show the search query up top but if there is no content to the query (as in no PRs matched), we should show the onboarding page in the search results panel. This onboarding page should be identical except for the description of the tab (Which should describe the PRs tab instead of the Agents tab).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/tab_onboarding_quickstart.md`

> # Plan: Tab Quick-Start Onboarding Redesign (Agents + PRs tabs)
> ## Problem & Goals
> The Agents and PRs tabs each show a rich, multi-card onboarding page when there is nothing else interesting to display.
> Three problems to solve:
> 1. **The current guide content is valuable but too heavy for an empty-state page.** It should be preserved verbatim
>    behind the existing `,?` (leader `tab_guide`) pop-up modal, which already renders the same widgets today.
> 2. **The empty-state pages should become lightweight "quick starts":** a 1–2 sentence summary of what the tab is about,
>    followed by the 5–7 most valuable _global_ keymaps for someone getting started (launching an agent, configuring sase,
>    installing plugins, getting help, etc.). The two tabs' pages are identical except for the tab summary.
> 3. **The PRs-tab visibility logic is broken.** Today onboarding only shows when _zero ChangeSpecs exist anywhere AND

*See full plan file for details.*

