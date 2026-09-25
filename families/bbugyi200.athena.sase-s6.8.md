# Family: sase-s6.8

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-s6](../users/bbugyi200/machines/athena/hoods/sase-s6/README.md) / sase-s6.8

Owner: `bbugyi200.athena` · Hood: `sase-s6` · Members: 6 · Bead: [sase-s6.8](https://github.com/sase-org/sase--beads/blob/main/pages/sase-s6/sase-s6.8.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-s6.8--mon-0 [active]"]
  n1["sase-s6.8--plan [active]"]
  n0 --> n1
  n2["sase-s6.8--mon [active]"]
  n0 --> n2
  n3["sase-s6.8--2 [active]"]
  n0 --> n3
  n4["sase-s6.8--1 [active]"]
  n0 --> n4
  n5["sase-s6.8--mon-1 [failed]"]
  n0 --> n5
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-mon-0"></a>mon-0 | sase-s6.8--mon-0 | active | grok-4.6 / grok | 2026-08-23T10:24:13.128784+00:00 | 0 | — | — |
| <a id="member-plan"></a>plan | sase-s6.8--plan | active | grok-4.6 / grok | 2026-08-23T09:03:16.754300+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-s6.8--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-s6.8--plan/chat.md) |
| <a id="member-mon"></a>mon | sase-s6.8--mon | active | grok-4.6 / grok | 2026-08-23T09:50:08.801706+00:00 | 0 | — | — |
| <a id="member-2"></a>2 | sase-s6.8--2 | active | grok-4.6 / grok | 2026-08-23T10:40:55.287171+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-s6.8--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-s6.8--2/chat.md) |
| <a id="member-1"></a>1 | sase-s6.8--1 | active | grok-4.6 / grok | 2026-08-23T10:07:28.604319+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-s6.8--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-s6.8--1/chat.md) |
| <a id="member-mon-1"></a>mon-1 | sase-s6.8--mon-1 | failed | grok-4.6 / grok | 2026-08-23T11:02:06.609992+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-s6.8--mon-1/chat.md) |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-s6.1](../agents/bbugyi200.athena.sase-s6.1/README.md) | sase-s6 hood | active |
| [sase-s6.2](../agents/bbugyi200.athena.sase-s6.2/README.md) | sase-s6 hood | active |
| [sase-s6.3](../agents/bbugyi200.athena.sase-s6.3/README.md) | sase-s6 hood | active |
| [sase-s6.4](../agents/bbugyi200.athena.sase-s6.4/README.md) | sase-s6 hood | active |
| [sase-s6.5](../agents/bbugyi200.athena.sase-s6.5/README.md) | sase-s6 hood | active |
| [sase-s6.6](../agents/bbugyi200.athena.sase-s6.6/README.md) | sase-s6 hood | active |
| [sase-s6.7](../agents/bbugyi200.athena.sase-s6.7/README.md) | sase-s6 hood | active |
| [sase-s6.land](../agents/bbugyi200.athena.sase-s6.land/README.md) | sase-s6 hood | active |
