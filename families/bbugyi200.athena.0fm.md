# Family: 0fm

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [0fm](../users/bbugyi200/machines/athena/hoods/0fm/README.md) / 0fm

Owner: `bbugyi200.athena` · Hood: `0fm` · Members: 6

## Lineage

```mermaid
flowchart TD
  n0["0fm--mon-1 [failed]"]
  n1["0fm--gate [failed]"]
  n0 --> n1
  n2["0fm--plan [completed]"]
  n0 --> n2
  n3["0fm--code [active]"]
  n0 --> n3
  n4["0fm--mon-0 [failed]"]
  n0 --> n4
  n5["0fm--mon [failed]"]
  n0 --> n5
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon-1"></a>mon-1 | 0fm--mon-1 | failed | gpt-5.5 / codex | 2026-08-28T17:29:07.483199+00:00 | 0 | — | — |
| <a id="member-gate"></a>gate | 0fm--gate | failed | opus / claude | 2026-08-28T17:09:51.970187+00:00 → 2026-08-28T17:13:57.505806+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0fm--gate/chat.md) |
| <a id="member-plan"></a>plan | 0fm--plan | completed | opus / claude | 2026-08-28T17:01:44.501359+00:00 → 2026-08-28T17:09:58.891131+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.0fm--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.0fm--plan/chat.md) |
| <a id="member-code"></a>code | 0fm--code | active | gpt-5.5 / codex | 2026-08-28T17:14:03.432266+00:00 | [1](../agents/bbugyi200.athena.0fm--code/README.md#commits) | [Prompt](../agents/bbugyi200.athena.0fm--code/prompt.md) | — |
| <a id="member-mon-0"></a>mon-0 | 0fm--mon-0 | failed | gpt-5.5 / codex | 2026-08-28T17:28:30.435545+00:00 | 0 | — | — |
| <a id="member-mon"></a>mon | 0fm--mon | failed | gpt-5.5 / codex | 2026-08-28T17:27:43.503270+00:00 | 0 | — | — |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`70e2d52`](https://github.com/sase-org/sase/commit/70e2d5250765cbae1fdb892ee6bc00d7aed20199) | fix(task-types): require one plus-one for bug triage | 2026-08-28 13:51:00 EDT |
