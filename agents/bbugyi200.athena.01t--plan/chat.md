# Chat History - ace-run (01t--plan)

- **TIMESTAMP:** 2026-08-14 16:43:23 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 01t--plan

**Plan:** /home/bryan/.sase/plans/202608/agent_show_positional.md


## Prompt

#gh:gh_sase-org__sase The `sase agent show` command accepts a required `-n|--name` option. Can you help me make this a positional argument instead? Also, CLI options should never be required; that's what positional arguments are for. Can you add similar guidance to the sase/memory/cli_rules.md memory file?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/agent_show_positional.md`

> # Plan: Make `sase agent show` take the agent name positionally
> ## Goal
> Change the public invocation from `sase agent show -n NAME` / `--name NAME` to
> `sase agent show NAME`, and record the general CLI design rule that required inputs
> belong in positional arguments rather than required options. Keep the parser destination
> as `args.name` so the existing show handler and its rendering behavior remain unchanged.
> ## Scope and decisions
> - Remove `-n` / `--name` from `sase agent show`; do not retain a compatibility alias.
>   The accepted command contract is the required `NAME` positional, and omitting it or
>   using the old option syntax is a normal argparse usage error.

*See full plan file for details.*

