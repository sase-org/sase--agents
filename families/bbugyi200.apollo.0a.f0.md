# Family: 0a.f0

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [0a](../users/bbugyi200/machines/apollo/hoods/0a/README.md) / 0a.f0

Owner: `bbugyi200.apollo` · Hood: `0a` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["0a.f0--plan [completed]"]
  n1["0a.f0--code [active]"]
  n0 --> n1
  n2["0a.f0--gate [failed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | 0a.f0--plan | completed | gpt-6-astra / codex | 2026-09-17T18:35:30.862018+00:00 → 2026-09-17T18:41:57.993364+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.0a.f0--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.0a.f0--plan/chat.md) |
| <a id="member-code"></a>code | 0a.f0--code | active | gpt-5.5 / codex | 2026-09-17T18:43:07.860106+00:00 | [1](../agents/bbugyi200.apollo.0a.f0--code/README.md#commits) | [Prompt](../agents/bbugyi200.apollo.0a.f0--code/prompt.md) | — |
| <a id="member-gate"></a>gate | 0a.f0--gate | failed | gpt-6-astra / codex | 2026-09-17T18:42:46.633554+00:00 → 2026-09-17T18:43:03.968153+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.0a.f0--gate/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`5e4c866`](https://github.com/sase-org/sase/commit/5e4c866eb5e5a4b6385855404078bc7fc9074fe0) | feat(tui): move agent panel layout toggle into grouping picker | 2026-09-17 17:01:35 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [0a](../agents/bbugyi200.apollo.0a/README.md) | ancestor | completed |
| [0a.f0.f0](../agents/bbugyi200.apollo.0a.f0.f0/README.md) | descendant | waiting |
