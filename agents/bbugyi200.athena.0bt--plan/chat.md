# Chat History - ace-run (0bt--plan)

- **TIMESTAMP:** 2026-08-23 10:41:32 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 0bt--plan

**Plan:** /home/bryan/.sase/plans/202608/remove_legacy_commit_command.md


## Prompt

#gh:gh_sase-org__sase Can you help me fully remove the `sase commit` command, which should just be a thin wrapper around the `sase stitch create` command? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/remove_legacy_commit_command.md`

> # Plan
> ## Context and boundaries
> `sase stitch create` is already the canonical spelling, but the old top-level
> `sase commit` command remains registered as an alias. The alias is not isolated: its
> parser module owns the shared create flags, its handler module owns the canonical create
> implementation, the root entry point has a separate dispatch branch, and tests still
> exercise both spellings. Active Mercurial/Patch skills and several current or draft docs
> also direct users to the legacy command.
> Remove the command rather than warning or redirecting: after this tale, `sase commit`
> must be absent from root help, completion/spec output, the lazy command registry, and

*See full plan file for details.*

