# Chat History - ace-run (29--plan)

- **TIMESTAMP:** 2026-07-08 13:50:26 EDT
- **MODEL:** claude/opus
- **AGENT:** 29--plan
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260708_134533.md`

**Plan:** /home/bryan/.sase/plans/202607/agent_provider_setup_doc.md


## Prompt

#gh:gh_sase-org__sase Can you help me add a new docs/ markdown file that describes how to install and authenticate each of the agent CLI providers that sase currently supports?

- Make sure that we point back to the canonical documentation for installing the given agent CLI.
- Make sure to link to this doc from relevant installation documentation (e.g. we should probably link to this from the INSTALL.md file).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %model:opus %a:tale

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/agent_provider_setup_doc.md`

> # Plan: Add an "Agent Provider Setup" docs page (install + authenticate each supported CLI)
> ## Problem / Product context
> SASE orchestrates an existing coding-agent CLI; it does not ship or replace that CLI's install and authentication flow.
> Today the requirement "install and authenticate at least one provider CLI" is stated in several places (`INSTALL.md`,
> `README.md`, `docs/getting_started.md`, blog posts, and `sase doctor` output) but **no single page tells a user how to
> actually do it** — there are no per-provider install commands, auth commands, or links to each vendor's canonical docs.
> A new user who runs `sase doctor` and sees "provider not ready" has to hunt across five different vendors to fix it.
> Goal: add one focused docs page that, for every provider SASE currently supports, gives (1) the install command, (2) the
> authentication command/flow, and (3) a link to that vendor's **canonical** install documentation — then link to this
> page from the places that currently only state the requirement.

*See full plan file for details.*

