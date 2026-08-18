# Family: sase-p2.2

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-p2](../users/bbugyi200/machines/athena/hoods/sase-p2/README.md) / sase-p2.2

Owner: `bbugyi200.athena` · Hood: `sase-p2` · Members: 3 · Bead: [sase-p2.2](https://github.com/sase-org/sase--beads/blob/main/pages/sase-p2/sase-p2.2.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-p2.2--mon [failed]"]
  n1["sase-p2.2--1 [completed]"]
  n0 --> n1
  n2["sase-p2.2--plan [completed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon"></a>mon | sase-p2.2--mon | failed | grok-4.6 / grok | 2026-08-17T23:58:07.462435+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-p2.2--mon/chat.md) |
| <a id="member-1"></a>1 | sase-p2.2--1 | completed | grok-4.6 / grok | 2026-08-18T00:43:44.441303+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-p2.2--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-p2.2--1/chat.md) |
| <a id="member-plan"></a>plan | sase-p2.2--plan | completed | grok-4.6 / grok | 2026-08-17T23:12:27.721877+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-p2.2--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-p2.2--plan/chat.md) |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-p2.1](../agents/bbugyi200.athena.sase-p2.1/README.md) | sase-p2 hood | completed |
| [sase-p2.3](bbugyi200.athena.sase-p2.3.md) (family · 11) | sase-p2 hood | completed 6, failed 5 |
| [sase-p2.4](bbugyi200.athena.sase-p2.4.md) (family · 5) | sase-p2 hood | completed 3, failed 2 |
| [sase-p2.land](bbugyi200.athena.sase-p2.land.md) (family · 3) | sase-p2 hood | active 1, completed 1, failed 1 |
