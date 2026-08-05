# Chat History - ace-run (qi--plan)

- **TIMESTAMP:** 2026-07-31 13:13:52 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** qi--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-qi__plan-260731_130446.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-qi__code-260731_130446.md`

**Plan:** /home/bryan/.sase/plans/202607/bead_id_shorthand.md


## Prompt

#gh:gh_sase-org__sase We currently need to specify the full bead ID (ex: `sase-a1`) for all `sase bead` sub-commands that take bead IDs as arguments (e.g. the `sase bead show` command, the `sase bead update` command, etc...). Can you help me make it so we can just use the alphanumeric part of the bead ID (ex: `a1`) as a shorthand? This should be easy enough since any full bead ID is expected to contain a dash, whereas the alphanumeric parts of bead IDs never will. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/bead_id_shorthand.md`

> # Plan: Accept dash-free shorthand in `sase bead` ID arguments
> ## Outcome
> Users can pass `a1` anywhere a `sase bead` subcommand currently expects the full ID `sase-a1`. Hierarchical IDs use the
> entire dash-free suffix, so `a1.2` resolves to `sase-a1.2`. Existing full IDs continue to work unchanged, including IDs
> whose project prefix itself contains dashes. Resolution happens against the active bead store, but canonical full IDs
> remain the only form written to bead records, dependency edges, events, mutation summaries, agent metadata, page paths,
> and command output.
> This is a `tale` because the core resolver, shell integration, documentation, and tests form one bounded change that a
> single implementation agent can complete and verify coherently. Splitting them would create a period where the Rust fast
> path and Python slow path disagree about accepted CLI syntax.

*See full plan file for details.*

