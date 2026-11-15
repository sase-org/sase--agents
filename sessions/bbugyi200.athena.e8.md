# Session: e8

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [e8](../users/bbugyi200/machines/athena/hoods/e8/README.md) / e8

Owner: `bbugyi200.athena` · Hood: `e8` · Members: 2

## Lineage

```mermaid
flowchart TD
  n0["e8--code [active]"]
  n1["e8--plan [dismissed]"]
  n0 --> n1
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-code"></a>code | e8--code | active | gpt-5.6-sol / codex | 2026-07-19T02:41:51.543244+00:00 | [1](../agents/bbugyi200.athena.e8--code/README.md#commits) | — | — |
| <a id="member-plan"></a>plan | e8--plan | dismissed | claude-fable-5 / claude | 2026-07-18T22:33:01.586864 → 2026-07-18T23:19:57.897692 | 0 | [Prompt](../agents/bbugyi200.athena.e8--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.e8--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | — | `185469e` | fix(plugins): preflight stale local install sources | 2026-07-18 23:19:24 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [e8.f0](../agents/bbugyi200.athena.e8.f0/README.md) | descendant | dismissed |
