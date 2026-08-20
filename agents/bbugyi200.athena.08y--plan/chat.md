# Chat History - ace-run (08y--plan)

- **TIMESTAMP:** 2026-08-20 16:34:28 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 08y--plan

**Plan:** /home/bryan/.sase/plans/202608/pluggable_finalizers.md


## Prompt

#gh:gh_sase-org__sase Sase's commit finalizer is currently a hard-coded part of the system. Can you
help me generalize the concept of sase's finalizer so users can define their own
finalizers via plugins and/or configuration?

- I think we should also support a new `%final` directive to override the finalizer for
  a specific sase agent.
  - I'm thinking this could then default to something like `%final:commit` if not used
    explicitly in a sase agent's prompt?
- One way to implement this is to add a new `/sase_final` xprompt skill and tell agents
  that they must invoke it at the end of every turn (sase agents that get intentionally
  terminated early--when using their /sase_plan or /sase_monitor skills, for
  example--are exempt).
  - The finalizer could then force a new turn if the agent doesn't use /sase_final for
    some reason (and then fail if the agent doesn't use /sase_final on that turn
    either).
  - This skill could instruct agents how to use a new `sase final` command to persist
    some JSON data somewhere that is associated with that agent and can be read,
    validated, and acted on (e.g. by creating commits, creating task beads, etc...) by
    the finalizer.
  - We should figure out a way for agents to specify the commits/stitches that should be
    created for each repo that contains files that the agent modified using the
    `sase final` command. We'll also need to be careful that we don't break sase's
    current merge conflict workflow (e.g. make sure merge conflicts are still always
    caught and handled by sase agents--when they can't be auto-resolved). Think hard
    about how to get this right.
    - One new requirement we should add: sase agents that do not commit to certain repos
      should be required to specify a refusal reason via the `sase final` command (so we
      have some more insight when the finalizer fails because an agent refused to commit
      detected file changes).
- Sase's commit finalizer is such a critical part of sase that I think this feature
  belongs behind a feature flag.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 Review
@research:202608/finalizer_protocol_and_extensibility/finalizer_protocol_and_extensibility.md
for inspiration before writing your plan. %w(runners=100)

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/pluggable_finalizers.md`

> # Plan: Host-owned pluggable finalizer protocol
> This plan is derived from
> `research:202608/finalizer_protocol_and_extensibility/finalizer_protocol_and_extensibility.md`
> and a current-code audit of the invocation seam, commit finalizer, baseline capture,
> commit checkpoint/result ledgers, prompt directives, generated skill sources, plugin
> inventory, and configuration merge path.
> ## 1. Problem and desired outcome
> `src/sase/llm_provider/_invoke.py` currently calls `run_commit_finalizer()` directly
> after every successful provider invocation. That controller is much more than a stop
> hook: it identifies the primary and opened repositories, protects pre-run dirt,

*See full plan file for details.*

