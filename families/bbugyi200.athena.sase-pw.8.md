# Family: sase-pw.8

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-pw](../users/bbugyi200/machines/athena/hoods/sase-pw/README.md) / sase-pw.8

Owner: `bbugyi200.athena` · Hood: `sase-pw` · Members: 5 · Bead: [sase-pw.8](https://github.com/sase-org/sase--beads/blob/main/pages/sase-pw/sase-pw.8.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-pw.8--2 [active]"]
  n1["sase-pw.8--plan [completed]"]
  n0 --> n1
  n2["sase-pw.8--mon-0 [failed]"]
  n0 --> n2
  n3["sase-pw.8--1 [completed]"]
  n0 --> n3
  n4["sase-pw.8--mon [failed]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-2"></a>2 | sase-pw.8--2 | active | grok-4.6 / grok | 2026-08-18T19:47:09.867120+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-pw.8--2/prompt.md) | — |
| <a id="member-plan"></a>plan | sase-pw.8--plan | completed | grok-4.6 / grok | 2026-08-18T18:13:28.015946+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-pw.8--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-pw.8--plan/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-pw.8--mon-0 | failed | grok-4.6 / grok | 2026-08-18T19:34:01.452978+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-pw.8--mon-0/chat.md) |
| <a id="member-1"></a>1 | sase-pw.8--1 | completed | grok-4.6 / grok | 2026-08-18T19:23:52.097192+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-pw.8--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-pw.8--1/chat.md) |
| <a id="member-mon"></a>mon | sase-pw.8--mon | failed | grok-4.6 / grok | 2026-08-18T18:37:46.301845+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-pw.8--mon/chat.md) |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-pw.1](../agents/bbugyi200.athena.sase-pw.1/README.md) | sase-pw hood | completed |
| [sase-pw.2](../agents/bbugyi200.athena.sase-pw.2/README.md) | sase-pw hood | completed |
| [sase-pw.3](../agents/bbugyi200.athena.sase-pw.3/README.md) | sase-pw hood | completed |
| [sase-pw.4](../agents/bbugyi200.athena.sase-pw.4/README.md) | sase-pw hood | completed |
| [sase-pw.5](bbugyi200.athena.sase-pw.5.md) (family · 7) | sase-pw hood | completed 4, failed 3 |
| [sase-pw.6](../agents/bbugyi200.athena.sase-pw.6/README.md) | sase-pw hood | active |
| [sase-pw.7](bbugyi200.athena.sase-pw.7.md) (family · 5) | sase-pw hood | active 1, completed 2, failed 2 |
| [sase-pw.9](../agents/bbugyi200.athena.sase-pw.9/README.md) | sase-pw hood | waiting |
| [sase-pw.land](../agents/bbugyi200.athena.sase-pw.land/README.md) | sase-pw hood | waiting |
