# Session: g0

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [g0](../users/bbugyi200/machines/athena/hoods/g0/README.md) / g0

Owner: `bbugyi200.athena` · Hood: `g0` · Members: 2

## Lineage

```mermaid
flowchart TD
  n0["g0--plan [dismissed]"]
  n1["g0--code [completed]"]
  n0 --> n1
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | g0--plan | dismissed | claude-fable-5 / claude | 2026-07-20T09:17:18.506687 → 2026-07-20T09:44:25.180276 | 0 | [Prompt](../agents/bbugyi200.athena.g0--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.g0--plan/chat.md) |
| <a id="member-code"></a>code | g0--code | completed | gpt-5.6-sol / codex | 2026-07-20T13:30:51.684796+00:00 | [1](../agents/bbugyi200.athena.g0--code/README.md#commits) | — | [Chat](../agents/bbugyi200.athena.g0--code/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | — | `88c1a7b` | feat(test): gate parallel suites by host capacity | 2026-07-20 09:44:14 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [g0.f0](../agents/bbugyi200.athena.g0.f0/README.md) | descendant | dismissed |
