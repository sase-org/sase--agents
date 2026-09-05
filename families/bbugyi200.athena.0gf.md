# Family: 0gf

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [0gf](../users/bbugyi200/machines/athena/hoods/0gf/README.md) / 0gf

Owner: `bbugyi200.athena` · Hood: `0gf` · Members: 5

## Lineage

```mermaid
flowchart TD
  n0["0gf--plan [completed]"]
  n1["0gf--code [completed]"]
  n0 --> n1
  n2["0gf--gate [failed]"]
  n0 --> n2
  n3["0gf--mon [failed]"]
  n0 --> n3
  n4["0gf--1 [active]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | 0gf--plan | completed | gpt-6-astra / codex | 2026-09-05T21:37:47.242139+00:00 → 2026-09-05T21:45:13.489456+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.0gf--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.0gf--plan/chat.md) |
| <a id="member-code"></a>code | 0gf--code | completed | sonnet / claude | 2026-09-05T21:49:50.193273+00:00 → 2026-09-05T22:07:41.869134+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.0gf--code/prompt.md) | [Chat](../agents/bbugyi200.athena.0gf--code/chat.md) |
| <a id="member-gate"></a>gate | 0gf--gate | failed | gpt-6-astra / codex | 2026-09-05T21:45:06.113143+00:00 → 2026-09-05T21:49:43.300579+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0gf--gate/chat.md) |
| <a id="member-mon"></a>mon | 0gf--mon | failed | sonnet / claude | 2026-09-05T22:07:15.394955+00:00 → 2026-09-05T22:17:27.911783+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0gf--mon/chat.md) |
| <a id="member-1"></a>1 | 0gf--1 | active | sonnet / claude | 2026-09-05T22:17:46.955252+00:00 | [1](../agents/bbugyi200.athena.0gf--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.0gf--1/prompt.md) | — |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 1 | sase | [`ee35836`](https://github.com/sase-org/sase/commit/ee358364ae7b7b87fd9d69b09142c6cee7ed776b) | fix(tui): always hide STARTING agent rows from the Agents tab | 2026-09-05 18:29:41 EDT |
