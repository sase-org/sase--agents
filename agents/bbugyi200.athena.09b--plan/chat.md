# Chat History - ace-run (09b--plan)

- **TIMESTAMP:** 2026-09-08 17:34:49 EDT
- **MODEL:** codex/gpt-6-astra
- **AGENT:** 09b--plan

## Prompt

#gh:gh_sase-org__sase Can you help me split out the `runners` and `priority` kwargs, which are
specific to sase's agent queue logic, to a new `%q/%queue` directive? %w(runners=3)

- Make sure this directive has all the same completion support in the prompt input
  widget and external editors (via LSP support) as other directives.
- The `runners` kwarg should also be supported as a positional argument (`%q:5` should
  be equivalent to the current `%w(runners=5)`, for example).
- The `priority` kwarg should also support a `p` shorthand (so, for example, `%q(p=20)`
  should be equivalent to `%q(priority=20)` which should be equivalent to the current
  `%w(priority=20)`).
- Make sure you thoroughly search all linked repos for references to these keywords and
  convert them over to using this new directive. I think some of my chops defined in the
  bugyi-chops repo might need updating as well.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

# Gate handoff

This agent handed the remaining decision to a gate shell.
Decision: Epic ready for review: queue_directive.md
Gate ID: f546d9bb-f3da-4993-99fe-8a34362a2d43
Inspect with: sase gate show --id f546d9bb-f3da-4993-99fe-8a34362a2d43 --kind epic_plan
Gate shell: 09b--gate

