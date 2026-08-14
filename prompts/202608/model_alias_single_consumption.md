- **PLAN:**
  [202608/model_alias_single_consumption.md](https://github.com/sase-org/sase--plans/blob/main/202608/model_alias_single_consumption.md)
- **AGENTS:**
  - [bbugyi200.athena.00i.f0--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.00i.f0.md)

%xprompts_enabled:false

# Previous Conversation

**User:**

Are the models in the model pool for the `@smarter` model alias being iterated over
evenly (i.e. each model in the pool is used equally) when used by not default (since
`@smarter` is the default value of the special `@default` model alias). If not, use your
/sase_plan skill to plan the appropriate changes.

**Assistant:**

I’ll trace alias resolution and pool selection, then verify the behavior with the
relevant tests. If `@smarter` is not balanced when selected explicitly, I’ll use the
`/sase_plan` workflow to produce the implementation plan.

The resolution path is designed to share a single cursor owned by `smarter`: an
implicit/no-`%model` launch follows `@default → @smarter`, reaches the `smarter` pool,
and advances that pool’s cursor once. I’m checking the launch-level regression tests
now, including the availability caveat.

Yes—assuming you mean when `@smarter` is reached through `@default` or a launch without
`%model`.

- `@default` delegates to `@smarter`, whose pool currently contains Codex and Claude
  models
  ([model_alias_defaults.yml](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/llm_provider/model_alias_defaults.yml:14)).
- Each real launch advances the round-robin cursor exactly once
  ([_invoke.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/llm_provider/_invoke.py:188)).
- The cursor is keyed to the pool-owning alias, `smarter`, so direct `@smarter`,
  `@default`, and other aliases delegating to `@smarter` share one rotation
  ([load_balancing.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/src/sase/llm_provider/load_balancing.py:212)).
- Four focused tests passed, including consecutive default launches selecting successive
  `@smarter` members.

The rotation only includes available providers; unavailable members are skipped.
Preview/display resolution also does not advance the cursor. No changes or `/sase_plan`
plan are needed.

---

%xprompts_enabled:true

# New Query

Review the last few sase agents I've launched without the `%model` directive and verify
this claim. Is it true? If not, use your /sase_plan skill to plan the appropriate
changes.
