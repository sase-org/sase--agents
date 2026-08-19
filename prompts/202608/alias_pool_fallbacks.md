- **PLAN:**
  [202608/alias_pool_fallbacks.md](https://github.com/sase-org/sase--plans/blob/main/202608/alias_pool_fallbacks.md)
- **AGENTS:**
  - [bbugyi200.athena.089--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.089.md)

Can you help me add support to model alias pools for fallbacks?

- Currently, fallbacks are supported via the `||` syntax, but I don't think they can be
  used with model alias pools.
- Let's use the
  `(<p1>/<m1>@<e1> | <p2>/<m2>@<e2> | ... | <pN>/<mN>@<eN>) || <p3>/<m3>@<e3>` syntax to
  support this.
- Namely, if the `<p1>`, `<p2>`, ...,`<pN>` providers are all unavailable (e.g. not
  installed or disabled), then `<p3>/<m3>@<e3>` should be used as the model for that
  model alias.
- As our first use-case for this syntax, let's set the default value for the `@large`
  model alias to `(claude/opus@xhigh | codex/gpt-5.6-sol@xhigh) || grok/grok-4.6@xhigh`,
  so `grok/grok-4.6@xhigh` is used for the `@large` model alias if neither of the claude
  or codex LLM providers are available.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
