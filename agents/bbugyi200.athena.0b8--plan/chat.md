# Chat History - ace-run (0b8--plan)

- **TIMESTAMP:** 2026-08-22 18:14:36 UTC
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 0b8--plan

**Plan:** /home/bryan/.sase/plans/202608/typed_launch_units.md


## Prompt

#gh:gh_sase-org__sase Can you help me implement the new `%if` and `%proc` directives and add support
for stand-alone proc shells, as described by the standalone_proc_launch_units.md and conditional_launch_admission.md files in the research
sidecar repo?

- Make sure these directives have excellent completion in the prompt input widget and
  external editors (via LSP support).
- Make sure the agents tab has excellent (visually appealing) support for stand-alone
  proc shells.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/typed_launch_units.md`

> # Plan: Conditional launch admission and stand-alone proc launch units
> ## Sources and verified current state
> This epic implements the contracts in these audited research artifacts from the
> `sase--research` sidecar:
> - `research:202608/standalone_proc_launch_units/standalone_proc_launch_units.md`
> - `research:202608/conditional_launch_admission/conditional_launch_admission.md`
> The current launch path expands a prompt into agent-shaped segments in Python, assigns
> agent names, applies agent-only normalization, and only then asks the Rust core for
> fanout planning. Bare `%wait` is rewritten to the preceding agent name. That ordering
> cannot represent a proc without inventing an agent, and it cannot prune a skipped unit

*See full plan file for details.*

