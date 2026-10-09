# Session: 60

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [apollo](../users/bbugyi200/machines/apollo/README.md) / [60](../users/bbugyi200/machines/apollo/hoods/60/README.md) / 60

Owner: `bbugyi200.apollo` · Hood: `60` · Members: 6

## Lineage

```mermaid
flowchart TD
  n0["60--mon-0 [failed]"]
  n1["60--code [completed]"]
  n0 --> n1
  n2["60--gate [failed]"]
  n0 --> n2
  n3["60--plan [active]"]
  n0 --> n3
  n4["60--mon [failed]"]
  n0 --> n4
  n5["60--1 [completed]"]
  n0 --> n5
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon-0"></a>mon-0 | 60--mon-0 | failed | muse-spark-1.3-contributor / muse | 2026-10-09T11:36:28.739334+00:00 → 2026-10-09T12:55:13.529650+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.60--mon-0/chat.md) |
| <a id="member-code"></a>code | 60--code | completed | muse-spark-1.3-contributor / muse | 2026-10-09T09:57:41.263685+00:00 → 2026-10-09T10:28:15.118632+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.60--code/chat.md) |
| <a id="member-gate"></a>gate | 60--gate | failed | opus / claude | 2026-10-09T09:56:35.553262+00:00 → 2026-10-09T09:56:57.051850+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.60--gate/chat.md) |
| <a id="member-plan"></a>plan | 60--plan | active | opus / claude | 2026-10-09T09:39:13.921527+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.60--plan/prompt.md) | [Chat](../agents/bbugyi200.apollo.60--plan/chat.md) |
| <a id="member-mon"></a>mon | 60--mon | failed | muse-spark-1.3-contributor / muse | 2026-10-09T10:26:19.051604+00:00 → 2026-10-09T11:27:54.404100+00:00 | 0 | — | [Chat](../agents/bbugyi200.apollo.60--mon/chat.md) |
| <a id="member-1"></a>1 | 60--1 | completed | muse-spark-1.3-contributor / muse | 2026-10-09T11:29:01.409029+00:00 → 2026-10-09T11:38:40.945457+00:00 | 0 | [Prompt](../agents/bbugyi200.apollo.60--1/prompt.md) | [Chat](../agents/bbugyi200.apollo.60--1/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| — | sase | [`73b7db3`](https://github.com/sase-org/sase/commit/73b7db3afbd1c9951be5703247624ee58427728f) | fix: hide audit launcher marker notifications | 2026-07-11 14:39:15 EDT |
