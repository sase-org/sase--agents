#gh:gh_sase-org__sase #fork:wv %w:sase-il.land.w0 Can you help me make the following changes to these
defaults?:

- Add a new `@smarter` model alias that defaults to
  `codex/gpt-5.6-sol@xhigh | claude/opus@xhigh`.
- `@default` should map to `@smarter`, so the .
- Let's change the default of the existing `@smart` model alias to
  `codex/gpt-5.5@xhigh | claude/sonnet@xhigh`.
- Change the default of the existing `@cheap` model alias to use
  `claude/sonnet@high | codex/gpt-5.5@high`
- The `@medium_worker` model alias should map to `@smart` and the `@large_worker` should
  be changed to map to `@smarter`.

#plan #m_opus