# Agent: 17q--plan

[Agent Hoods](../../README.md) / [bbugyi200](../../users/bbugyi200/README.md) / [athena](../../users/bbugyi200/machines/athena/README.md) / [17q](../../users/bbugyi200/machines/athena/hoods/17q/README.md) / [17q](../../sessions/bbugyi200.athena.17q.md) / 17q--plan

**Global name:** `bbugyi200.athena.17q--plan` · **State:** completed · **Source run:** `run-6dd7b773b7f196f27b0c2b1079f6e5af`

**Owner:** `bbugyi200.athena` · **Project:** sase · **Hood:** 17q

## Summary

- Model: opus
- Provider: claude
- Timing: 2026-11-03T20:42:21.798388+00:00 → 2026-11-03T20:48:21.727544+00:00
- Commits: 0
- Variables: [3](#variables)

## Files

[Chat](chat.md) · [Prompt](prompt.md)

## Variables

| Variable | Value |
|---|---|
| `plan_assessment` | {alternatives\_rejected: {config\_field: A per-run, temporary evaluation knob is not a lasting user preference., delete\_now\_revert\_later: Loses per-run choice; the revert would conflict with later edit… |
| `plan_confidence` | 0.8 |
| `plan_verdict` | endorse\_with\_caveats |

#### plan_assessment

```yaml
alternatives_rejected:
  config_field: A per-run, temporary evaluation knob is not a lasting user preference.
  delete_now_revert_later: Loses per-run choice; the revert would conflict with later edits to the same lines.
  sase_feature_flag: Flags are sase-project only; wrong scope for a plugin macro.
caveats:
  - You may not need the change to start evaluating. Plain `#research_swarm` (no linker), `#research`, and `#research/more` already publish real tables, so `bob ref create` table rendering can be judged on existing reports today.
  - The real lever is the renderer. Per pandoc's pipe-table rule, when any row exceeds `--columns` (72), column widths come from the separator dash counts, so `|---|---|` gives equal-width wrapped columns. A renderer-side fix (a Lua filter that sizes columns from content, or proportional separator dashes) would help every producer, not just linker runs.
  - Interface creep: this is the 24th input on an already large macro, and temporary inputs tend to stick. Decide by a date whether to delete it.
  - Only linker runs (`linker`/`image`/`diagrams`/`audio`) are affected; the plan deliberately does not make the flag imply the linker.
suggested_follow_up: After a few real PDFs with tables, either delete the input and its true arms, or keep tables and fix widths in the renderer instead.
summary: A default-off per-run macro input is the right reversible step: it gives the end state you want today, keeps the carefully tuned conversion rule tested instead of rotting in git history, and removal later is a mechanical delete of the true arms.
why_right:
  - Easier to re-enable than `git revert c787c88`; that revert would now conflict with later diagram-era edits that reference the rule ("converted from a table into a list", the `:::` sentence, "or a diagram").
  - Per-run granularity fits an evaluation: you can A/B the same topic with and without conversion.
  - Matches the existing linker-modifier pattern (`linker_model`, `audio_edition`): it never adds an agent, so no execution-matrix churn.
  - A SASE feature flag does not fit: flags are a sase-project concern, and this lives in a plugin as a per-run choice.
```

Values are truncated for display; see [meta.json](meta.json) for the full values.
