# Family: rp.f2

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [rp](../users/bbugyi200/machines/athena/hoods/rp/README.md) / rp.f2

Owner: `bbugyi200.athena` · Hood: `rp` · Members: 2

## Lineage

```mermaid
flowchart TD
  n0["rp.f2--code [completed]"]
  n1["rp.f2--plan [active]"]
  n0 --> n1
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-code"></a>code | rp.f2--code | completed | gpt-5.6-sol / codex | 2026-08-02T11:41:09.787369+00:00 | [1](../agents/bbugyi200.athena.rp.f2--code/README.md#commits) | — | [Chat](../agents/bbugyi200.athena.rp.f2--code/chat.md) |
| <a id="member-plan"></a>plan | rp.f2--plan | active | gpt-5.6-sol / codex | 2026-08-02T11:31:32.840312+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.rp.f2--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.rp.f2--plan/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`e4c13b3`](https://github.com/sase-org/sase/commit/e4c13b3e837b8d8464013cf52194a596a1c4ac9b) | feat(llm): add provider-specific coder defaults | 2026-08-02 08:16:50 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [rp](bbugyi200.athena.rp.md) (family · 2) | ancestor | active 1, completed 1 |
| [rp.f0](../agents/bbugyi200.athena.rp.f0/README.md) | rp hood | waiting |
