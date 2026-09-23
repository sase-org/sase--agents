# Family: 0pn

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [0pn](../users/bbugyi200/machines/athena/hoods/0pn/README.md) / 0pn

Owner: `bbugyi200.athena` · Hood: `0pn` · Members: 5

## Lineage

```mermaid
flowchart TD
  n0["0pn--gate [failed]"]
  n1["0pn--plan [completed]"]
  n0 --> n1
  n2["0pn--mon [failed]"]
  n0 --> n2
  n3["0pn--1 [active]"]
  n0 --> n3
  n4["0pn--code [completed]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-gate"></a>gate | 0pn--gate | failed | opus / claude | 2026-09-23T11:00:11.887111+00:00 → 2026-09-23T11:00:54.758784+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0pn--gate/chat.md) |
| <a id="member-plan"></a>plan | 0pn--plan | completed | opus / claude | 2026-09-23T03:52:52.316275+00:00 → 2026-09-23T06:10:56.563068+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.0pn--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.0pn--plan/chat.md) |
| <a id="member-mon"></a>mon | 0pn--mon | failed | muse-spark-1.3-contributor / muse | 2026-09-23T11:22:04.401547+00:00 → 2026-09-23T11:42:08.458523+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.0pn--mon/chat.md) |
| <a id="member-1"></a>1 | 0pn--1 | active | muse-spark-1.3-contributor / muse | 2026-09-23T11:42:32.659718+00:00 | [1](../agents/bbugyi200.athena.0pn--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.0pn--1/prompt.md) | — |
| <a id="member-code"></a>code | 0pn--code | completed | muse-spark-1.3-contributor / muse | 2026-09-23T11:01:17.983463+00:00 → 2026-09-23T11:22:31.001518+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.0pn--code/prompt.md) | [Chat](../agents/bbugyi200.athena.0pn--code/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 1 | sase | [`c87c9d1`](https://github.com/sase-org/sase/commit/c87c9d1aa9383d0d9bd5431b0339f72270100329) | fix(gate): repair Master Gate failures and shrink docs PDF under size gate | 2026-09-23 07:46:04 EDT |
