# Chat History - ace-run (97--plan)

- **TIMESTAMP:** 2026-07-15 11:39:04 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 97--plan

**Plan:** /home/bryan/.sase/plans/202607/generalize_toobig_split.md


## Prompt

#gh:gh_sase-org__sase The xprompts/toobig_split.yml xprompt workflow is not working (see how this is used in the chops configured in my chezmoi repo's sase_athena.yml file for context). This xprompt workflow is completely unnecessary however and should be generalized so I can use it from other repos. For that reason we should factor out the Python code from this xprompt workflow into its own script, which is defined in my chezmoi repo and run that script when the chop is run (instead of running an `agent` chop). Can you help me fix this / make this improvement? Run this script manually when you are done to verify that all of the expected (16 if I counted right--see the `toobig` output below) sase agents were launched (make sure that this script is smart enough to abort if another instance of it is running--this way if I update sase and axe tries to run this chop, we don't get duplicate agents).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/generalize_toobig_split.md`

> # Plan: Generalize the toobig split chop
> The current `xprompts/toobig_split.yml` workflow mixes scanning and fan-out logic into an inline Python xprompt, assumes
> the `sase` GitHub project, and requires an otherwise unnecessary wrapper agent. The athena axe configuration launches
> that workflow as an agent chop even though axe can discover and execute standalone chop scripts directly. The live
> scanner currently reports 18 qualifying files (7 below `src` and 11 below `tests`); this is the verification baseline at
> planning time, while the implementation will always derive the expected launch count from the scan itself so normal
> repository evolution cannot make the check stale.
> ## Implementation
> 1. Add a chezmoi-managed executable chop script with a generic `toobig_split` identity. It will accept the chop runner's
>    `--context` argument, resolve a configured SASE project through the supported machine-readable project CLI, and also

*See full plan file for details.*

