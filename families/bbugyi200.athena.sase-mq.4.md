# Family: sase-mq.4

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-mq](../users/bbugyi200/machines/athena/hoods/sase-mq/README.md) / sase-mq.4

Owner: `bbugyi200.athena` · Hood: `sase-mq` · Members: 3 · Bead: [sase-mq.4](https://github.com/sase-org/sase--beads/blob/main/pages/sase-mq/sase-mq.4.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-mq.4--plan [completed]"]
  n1["sase-mq.4--1 [active]"]
  n0 --> n1
  n2["sase-mq.4--mon [failed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-mq.4--plan | completed | grok-4.6 / grok | 2026-08-16T06:30:40.094311+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-mq.4--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-mq.4--plan/chat.md) |
| <a id="member-1"></a>1 | sase-mq.4--1 | active | grok-4.6 / grok | 2026-08-16T07:36:16.914193+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-mq.4--1/prompt.md) | — |
| <a id="member-mon"></a>mon | sase-mq.4--mon | failed | grok-4.6 / grok | 2026-08-16T07:22:17.958893+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-mq.4--mon/chat.md) |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-mq.1](../agents/bbugyi200.athena.sase-mq.1/README.md) | sase-mq hood | completed |
| [sase-mq.2](bbugyi200.athena.sase-mq.2.md) (family · 3) | sase-mq hood | completed 2, failed 1 |
| [sase-mq.3](bbugyi200.athena.sase-mq.3.md) (family · 2) | sase-mq hood | completed 2 |
| [sase-mq.5](../agents/bbugyi200.athena.sase-mq.5/README.md) | sase-mq hood | completed |
| [sase-mq.6](../agents/bbugyi200.athena.sase-mq.6/README.md) | sase-mq hood | completed |
| [sase-mq.7](../agents/bbugyi200.athena.sase-mq.7/README.md) | sase-mq hood | waiting |
| [sase-mq.land](../agents/bbugyi200.athena.sase-mq.land/README.md) | sase-mq hood | waiting |
