# Family: sase-mq.8.land

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-mq](../users/bbugyi200/machines/athena/hoods/sase-mq/README.md) / sase-mq.8.land

Owner: `bbugyi200.athena` · Hood: `sase-mq` · Members: 3 · Bead: [sase-mq.8](https://github.com/sase-org/sase--beads/blob/main/pages/sase-mq/sase-mq.8.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-mq.8.land--plan [active]"]
  n1["sase-mq.8.land--mon [failed]"]
  n0 --> n1
  n2["sase-mq.8.land--1 [active]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-mq.8.land--plan | active | gpt-5.6-sol / codex | 2026-08-16T10:07:18.222625+00:00 | [1](../agents/bbugyi200.athena.sase-mq.8.land--plan/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-mq.8.land--plan/prompt.md) | — |
| <a id="member-mon"></a>mon | sase-mq.8.land--mon | failed | gpt-5.6-sol / codex | 2026-08-16T10:31:21.742224+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-mq.8.land--mon/chat.md) |
| <a id="member-1"></a>1 | sase-mq.8.land--1 | active | gpt-5.6-sol / codex | 2026-08-16T10:41:44.187664+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-mq.8.land--1/prompt.md) | — |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| plan | sase | [`71012c5`](https://github.com/sase-org/sase/commit/71012c5c742c7ddc4cd4e5592927b0798778ff3e) | refactor(workspace): narrow operational lease internals | 2026-08-16 10:42:32 UTC |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-mq.8.1](../agents/bbugyi200.athena.sase-mq.8.1/README.md) | sase-mq.8 hood | completed |
| [sase-mq.8.2](../agents/bbugyi200.athena.sase-mq.8.2/README.md) | sase-mq.8 hood | completed |
| [sase-mq.8.3](../agents/bbugyi200.athena.sase-mq.8.3/README.md) | sase-mq.8 hood | completed |
| [sase-mq.8.4](../agents/bbugyi200.athena.sase-mq.8.4/README.md) | sase-mq.8 hood | completed |
| [sase-mq.1](../agents/bbugyi200.athena.sase-mq.1/README.md) | sase-mq hood | completed |
| [sase-mq.2](bbugyi200.athena.sase-mq.2.md) (family · 3) | sase-mq hood | completed 2, failed 1 |
| [sase-mq.3](bbugyi200.athena.sase-mq.3.md) (family · 2) | sase-mq hood | completed 2 |
| [sase-mq.4](bbugyi200.athena.sase-mq.4.md) (family · 3) | sase-mq hood | completed 2, failed 1 |
| [sase-mq.5](../agents/bbugyi200.athena.sase-mq.5/README.md) | sase-mq hood | completed |
| [sase-mq.6](../agents/bbugyi200.athena.sase-mq.6/README.md) | sase-mq hood | completed |
| [sase-mq.7](../agents/bbugyi200.athena.sase-mq.7/README.md) | sase-mq hood | completed |
| [sase-mq.land](bbugyi200.athena.sase-mq.land.md) (family · 2) | sase-mq hood | failed 2 |
