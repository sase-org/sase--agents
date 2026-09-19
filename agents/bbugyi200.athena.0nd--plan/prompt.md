#gh:gh_sase-org__sase Can you help me update the default values used by sase's builtin model aliases?
Review the model_alias_budget_policy.md file in the research sidecar repo for context
and inspiration before planning. Note that you should use the recommended model alias
set, but will need to modify them to get them to work with sase I believe (for example,
`claude/claude-fable-5-1` and `claude/claude-opus-5` aren't valid model alias, right?).

#plan %m:grok-4.6