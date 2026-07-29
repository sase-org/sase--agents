# Chat History - ace-run (nr--1)

- **TIMESTAMP:** 2026-07-29 06:35:38 EDT
- **MODEL:** claude/opus
- **AGENT:** nr--1

**Plan:** /home/bryan/.sase/plans/202607/h_collapse_lanes_label.md


## Prompt

#gh:gh_sase-org__sase The `H` (collapse houses) keymap seems to have the wrong description (see #sshot). Can you help me fix this? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

%xprompts_enabled:false
### Questions and Answers

#### Q1: H label

> In the screenshot, H is labeled "collapse houses" while a family member (np--plan) is selected inside the one open np family. Internally that label is consistent with the code, help modal, and docs/ace.md — so which part reads wrong to you?

- [x] **Wrong word: houses** — "House" is only a metaphor in the glossary; the real user-facing terms are lane / hood / family / clan. Footer (and help modal + docs) should use the real term instead.
- [ ] **Wrong number: plural** — Only one house is open here, so it should read "collapse house" (singular) and only pluralize when 2+ open houses would be collapsed.
- [ ] **Wrong scope: should name the row** — With a family member selected, H should advertise what it does to that row (e.g. "collapse family"), not the group-wide sweep label.
- [ ] **Wrong behavior: H does something else** — Pressing H here actually does something other than fully collapsing open houses (e.g. collapses the group/clan, or does nothing). The label is fine; the availability logic is buggy.
- [ ] **Something else** — None of the above — I will describe what I expected H to say/do.

%xprompts_enabled:true

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/h_collapse_lanes_label.md`

> # Rename the `H` "houses" vocabulary to the real SASE term "lanes"
> ## Problem
> The ACE Agents-tab footer advertises the uppercase `H` ladder's first step as `H collapse houses`.
> "House" is not a real SASE term. It has no glossary entry of its own. It appears exactly once in the glossary, inside
> the **Agent Lane** definition, and only as an explanatory metaphor:
> > We think of an agent lane like an agent's house (i.e. where they live). When agents are single, they live in their own
> > lane.
> The user-facing vocabulary for the Agents tree is **lane / hood / family / clan / tribe**. So the footer chip, the help
> modal row, the command-palette entry, the `Binding` descriptions, and the prose in `docs/` are all naming a concept with
> a word that a user cannot look up.

*See full plan file for details.*

