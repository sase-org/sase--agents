# Session: 0s

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [0s](../users/bbugyi200/machines/apollo/hoods/0s/README.md) / 0s

Owner: `bbugyi200.apollo` · Hood: `0s` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["0s--code [completed]"]
  n1["0s--plan [dismissed]"]
  n0 --> n1
  n2["0s--gate [failed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-code"></a>code | 0s--code | completed | grok-4.6 / grok | 2026-09-19T13:48:06.577808+00:00 → 2026-09-19T15:15:42.697826+00:00 | [1](../agents/bbugyi200.apollo.0s--code/README.md#commits) | [Prompt](../agents/bbugyi200.apollo.0s--code/prompt.md) | [Chat](../agents/bbugyi200.apollo.0s--code/chat.md) |
| <a id="member-plan"></a>plan | 0s--plan | dismissed | grok-4.6 / grok | 2026-09-19T09:31:42.106692 → 2026-09-19T09:47:27.759656 | 0 | [Prompt](../agents/bbugyi200.apollo.0s--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.0s--plan/chat.md) |
| <a id="member-gate"></a>gate | 0s--gate | failed | grok-4.6 / grok | 2026-09-19T13:47:45.062389+00:00 → 2026-09-19T13:48:01.425507+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.0s--gate/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | — | `d57cf2a` | chore: Add SDD prompt and plan for agents\_var\_namespace | 2026-06-03 01:23:03 EDT |
| — | — | `0b84b94` | chore: Add SDD prompt and plan for update\_confirm\_commits | 2026-07-07 14:24:34 EDT |
| — | — | `9c9caa6` | fix(tui): summarize multi-repo update commits | 2026-07-07 14:33:43 EDT |
| code | — | `ea5fc2b` | feat(ace): show launch-effective default effort on the TUI launch-default pill | 2026-09-19 11:13:27 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [0s.f0](bbugyi200.apollo.0s.f0.md) (session · 3) | descendant | completed 2, failed 1 |
| [0s.f0](../agents/bbugyi200.apollo.0s.f0/README.md) | descendant | waiting |
| [0s.f0.f0](bbugyi200.apollo.0s.f0.f0.md) (session · 3) | descendant | completed 2, failed 1 |
| [0s.f0.f0.w0](../agents/bbugyi200.apollo.0s.f0.f0.w0/README.md) | descendant | dismissed |
| [0s.f0.f0.w1](../agents/bbugyi200.apollo.0s.f0.f0.w1/README.md) | descendant | dismissed |
| [0s.f0.f0.w2](bbugyi200.apollo.0s.f0.f0.w2.md) (session · 3) | descendant | failed 3 |
| [0s.f0.f0.w2.w0](bbugyi200.apollo.0s.f0.f0.w2.w0.md) (session · 7) | descendant | completed 4, failed 3 |
