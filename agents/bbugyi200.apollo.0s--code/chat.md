# Chat History - ace-run (0s--code)

- **TIMESTAMP:** 2026-09-19 11:15:00 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** 0s--code

## Prompt

%model:@small
#gh:gh_sase-org__sase @plan:202609/tui_default_effort_indicator.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll read the implement skill and the approved plan, then start implementation.

I'll inspect the existing launch-default pill, peek token, and Launch Control refresh paths next.

I have the design; next I’ll add the peek path, snapshot rendering, Launch Control invalidation, tests, and docs.

I'll restore the `resolve_effective_default_provider_model` re-export so visual-startup stubs keep working.

The ACE top-bar launch-default pill now names the launch-effective default effort as well as the model, for example `GROK(grok-4.6)@high`. When that effort is unset, the label stays suffix-free.

What shipped:

- Calm cyan pill and tooltip append `@<effort>` / ` @ <effort>` from `resolve_effective_effort` (alias-borne, temporary `Ctrl+E` override, then `llm_provider.default_effort`). Configured `none` renders as `@none`.
- Off-thread worker stores effort on the launch-default snapshot. The 5-second tick still only peeks.
- New lock-free `effort_override_peek` plus `llm_effort_override.json` in the launch-default change token, including expiry without a rewrite.
- Launch Control writes always invalidate the cached default so effort edits show up immediately.
- Docs in `docs/ace.md` and `docs/llms.md`. Changelog is generated from the conventional commit, not edited by hand.

Gold temporary-model-override pills are unchanged. Visual startup still stubs `effort=None`.
