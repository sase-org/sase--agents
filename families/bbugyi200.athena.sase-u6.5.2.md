# Family: sase-u6.5.2

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-u6](../users/bbugyi200/machines/athena/hoods/sase-u6/README.md) / sase-u6.5.2

Owner: `bbugyi200.athena` · Hood: `sase-u6` · Members: 3 · Bead: [sase-u6.5.2](https://github.com/sase-org/sase--beads/blob/main/pages/sase-u6/sase-u6.5.2.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-u6.5.2--plan [active]"]
  n1["sase-u6.5.2--1 [active]"]
  n0 --> n1
  n2["sase-u6.5.2--mon [failed]"]
  n0 --> n2
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-u6.5.2--plan | active | sonnet / claude | 2026-08-26T17:28:32.481738+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-u6.5.2--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-u6.5.2--plan/chat.md) |
| <a id="member-1"></a>1 | sase-u6.5.2--1 | active | sonnet / claude | 2026-08-26T17:42:33.425773+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-u6.5.2--1/prompt.md) | — |
| <a id="member-mon"></a>mon | sase-u6.5.2--mon | failed | sonnet / claude | 2026-08-26T17:30:44.147579+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-u6.5.2--mon/chat.md) |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-u6.5.1](../agents/bbugyi200.athena.sase-u6.5.1/README.md) | sase-u6.5 hood | active |
| [sase-u6.5.land](../agents/bbugyi200.athena.sase-u6.5.land/README.md) | sase-u6.5 hood | active |
| [sase-u6.1](../agents/bbugyi200.athena.sase-u6.1/README.md) | sase-u6 hood | active |
| [sase-u6.2](../agents/bbugyi200.athena.sase-u6.2/README.md) | sase-u6 hood | active |
| [sase-u6.3](../agents/bbugyi200.athena.sase-u6.3/README.md) | sase-u6 hood | active |
| [sase-u6.4](bbugyi200.athena.sase-u6.4.md) (family · 5) | sase-u6 hood | active 3, failed 2 |
| [sase-u6.land](bbugyi200.athena.sase-u6.land.md) (family · 2) | sase-u6 hood | active 1, failed 1 |
