# Family: sase-mq.2

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-mq](../users/bbugyi200/machines/athena/hoods/sase-mq/README.md) / sase-mq.2

Owner: `bbugyi200.athena` · Hood: `sase-mq` · Members: 3 · Bead: [sase-mq.2](https://github.com/sase-org/sase--beads/blob/main/pages/sase-mq/sase-mq.2.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-mq.2--plan [completed]"]
  n1["sase-mq.2--1 [completed]"]
  n0 --> n1
  n2["sase-mq.2--mon [failed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-mq.2--plan | completed | grok-4.6 / grok | 2026-08-16T04:49:59.544066+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-mq.2--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-mq.2--plan/chat.md) |
| <a id="member-1"></a>1 | sase-mq.2--1 | completed | grok-4.6 / grok | 2026-08-16T05:24:11.288317+00:00 | [1](../agents/bbugyi200.athena.sase-mq.2--1/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-mq.2--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-mq.2--1/chat.md) |
| <a id="member-mon"></a>mon | sase-mq.2--mon | failed | grok-4.6 / grok | 2026-08-16T05:22:36.441068+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-mq.2--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 1 | sase | [`419c5a9`](https://github.com/sase-org/sase/commit/419c5a9fcdcce70bb42d3ebd22974ced71321163) | feat(workspace): add durable operational workspace leases | 2026-08-16 01:31:13 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-mq.1](../agents/bbugyi200.athena.sase-mq.1/README.md) | sase-mq hood | completed |
| [sase-mq.3](bbugyi200.athena.sase-mq.3.md) (family · 2) | sase-mq hood | active 2 |
| [sase-mq.4](../agents/bbugyi200.athena.sase-mq.4/README.md) | sase-mq hood | waiting |
| [sase-mq.5](../agents/bbugyi200.athena.sase-mq.5/README.md) | sase-mq hood | waiting |
| [sase-mq.6](../agents/bbugyi200.athena.sase-mq.6/README.md) | sase-mq hood | completed |
| [sase-mq.7](../agents/bbugyi200.athena.sase-mq.7/README.md) | sase-mq hood | waiting |
| [sase-mq.land](../agents/bbugyi200.athena.sase-mq.land/README.md) | sase-mq hood | waiting |
