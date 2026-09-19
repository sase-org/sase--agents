# Chat History - ace-run (0w--plan)

- **TIMESTAMP:** 2026-09-19 10:40:59 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** 0w--plan

## Prompt

#gh:gh_sase-org__sase Sase agents are running the `just check-full` command much more than they
should because of this project's instructions / memories. Can you help me fix this by
instructing agents to only run the `just check-full` command when they are explicitly
instructed to do so (i.e. to fix a CI failure)?

- Epic lander agents should stop running this command too which means we should, as a
  part of this change, stop giving them a default capacity (via the `%queue` directive)
  of `2`.
- The idea is that, if an agent makes changes that do not trigger the `just check`
  command to fail, but trigger the `just check-full` command to fail, we should treat
  that as a test infrastructure bug that is out-of-scope for the current agent's work.
- The `just check` command can still escalate to the full test suite if necessary (which
  should ideally be rare).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:grok-4.6@xhigh

## Response

# Gate handoff

This agent handed the remaining decision to a gate shell.
Decision: Tale ready for review: check_full_explicit_only.md
Gate ID: b9e5f7f4-c8a7-4032-bb3f-9722308ca657
Inspect with: sase gate show --id b9e5f7f4-c8a7-4032-bb3f-9722308ca657 --kind plan
Gate shell: 0w--gate

