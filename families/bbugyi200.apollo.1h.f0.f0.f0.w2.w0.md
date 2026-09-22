# Family: 1h.f0.f0.f0.w2.w0

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [1h](../users/bbugyi200/machines/apollo/hoods/1h/README.md) / 1h.f0.f0.f0.w2.w0

Owner: `bbugyi200.apollo` · Hood: `1h` · Members: 3

## Lineage

```mermaid
flowchart TD
  n0["1h.f0.f0.f0.w2.w0--plan [active]"]
  n1["1h.f0.f0.f0.w2.w0--code [active]"]
  n0 --> n1
  n2["1h.f0.f0.f0.w2.w0--gate [failed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | 1h.f0.f0.f0.w2.w0--plan | active | opus / claude | 2026-09-22T18:49:48.375650+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.1h.f0.f0.f0.w2.w0--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.1h.f0.f0.f0.w2.w0--plan/chat.md) |
| <a id="member-code"></a>code | 1h.f0.f0.f0.w2.w0--code | active | muse-spark-1.3-contributor / muse | 2026-09-22T19:16:10.949490+00:00 | [1](../agents/bbugyi200.apollo.1h.f0.f0.f0.w2.w0--code/README.md#commits) | [Prompt](../agents/bbugyi200.apollo.1h.f0.f0.f0.w2.w0--code/prompt.md) | — |
| <a id="member-gate"></a>gate | 1h.f0.f0.f0.w2.w0--gate | failed | opus / claude | 2026-09-22T19:15:51.020956+00:00 → 2026-09-22T19:16:06.057834+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.1h.f0.f0.f0.w2.w0--gate/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| code | sase | [`ecf795f`](https://github.com/sase-org/sase/commit/ecf795f5a37a41f17178a152120f4b039b5791be) | feat(ace): give the top-bar updates badge its own visual language | 2026-09-22 16:41:50 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [1h.f0.f0.f0.w2](bbugyi200.apollo.1h.f0.f0.f0.w2.md) (family · 5) | ancestor | completed 3, failed 2 |
| [1h.f0.f0.f0](bbugyi200.apollo.1h.f0.f0.f0.md) (family · 7) | ancestor | active 1, completed 3, failed 3 |
| [1h.f0.f0](bbugyi200.apollo.1h.f0.f0.md) (family · 3) | ancestor | active 1, completed 1, failed 1 |
| [1h.f0](bbugyi200.apollo.1h.f0.md) (family · 5) | ancestor | active 1, completed 2, failed 2 |
| [1h](bbugyi200.apollo.1h.md) (family · 3) | ancestor | active 1, completed 1, failed 1 |
| [1h.f0.f0.f0.w2.w0.w0](bbugyi200.apollo.1h.f0.f0.f0.w2.w0.w0.md) (family · 3) | descendant | active 2, failed 1 |
| [1h.f0.f0.f0.w2.w0.w0.w0](../agents/bbugyi200.apollo.1h.f0.f0.f0.w2.w0.w0.w0/README.md) | descendant | waiting |
| [1h.f0.f0.f0.w0](../agents/bbugyi200.apollo.1h.f0.f0.f0.w0/README.md) | 1h.f0.f0.f0 hood | waiting |
| [1h.f0.f0.f0.w1](../agents/bbugyi200.apollo.1h.f0.f0.f0.w1/README.md) | 1h.f0.f0.f0 hood | waiting |
