#gh:gh_sase-org__sase Can you help me drastically simplify sase's builtin model aliases and improve
the "Models" panel (triggered by the `,m` keymap)?

- We should maintain the ability for users to configure their own model aliases and
  model alias buckets, but all builtin buckets should be removed and all builtin model
  aliases should be removed except for the `@<size>_worker` model aliases, which
  currently live in the `phase_worker` bucket but should be top-level (i.e. no bucket)
  after this change.
- These `@<size>_worker` model aliases should be renamed to just `@<size>` (for example,
  the `@medium_worker` model alias should be renamed to `@medium`).
- These `@<size>` model aliases should have default values equal to the value currently
  used by the `@smart` / `@cheap` model alias variant that the corresponding
  `@<size>_worder` model alias is currently configured to use by default (for example,
  `@large` should have a default value of
  `claude/opus@xhigh | codex/gpt-5.6-sol@xhigh`).
- The `@default` model alias, which was never used explicitly anyway, should be removed
  in favor of using a sase config field (which should default to using `@large` for its
  value).
- Similarly, the `@epic_lander` and `@big_epic_lander` model aliases should be removed
  in favor of new sase config fields.
- Make sure that all of these config fields have their current values displayed on this
  re-designed panel somewhere (probably with the runner limit and the default effort
  level).
- #beau

#plan