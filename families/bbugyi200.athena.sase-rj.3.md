# Family: sase-rj.3

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-rj](../users/bbugyi200/machines/athena/hoods/sase-rj/README.md) / sase-rj.3

Owner: `bbugyi200.athena` · Hood: `sase-rj` · Members: 4 · Bead: [sase-rj.3](https://github.com/sase-org/sase--beads/blob/main/pages/sase-rj/sase-rj.3.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-rj.3--plan [completed]"]
  n1["sase-rj.3--1 [completed]"]
  n0 --> n1
  n2["sase-rj.3--mon [failed]"]
  n0 --> n2
  n3["sase-rj.3--mon-0 [active]"]
  n0 --> n3
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-plan"></a>plan | sase-rj.3--plan | completed | grok-4.6 / grok | 2026-08-20T18:24:10.985932+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-rj.3--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-rj.3--plan/chat.md) |
| <a id="member-1"></a>1 | sase-rj.3--1 | completed | grok-4.6 / grok | 2026-08-20T19:25:36.042418+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-rj.3--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-rj.3--1/chat.md) |
| <a id="member-mon"></a>mon | sase-rj.3--mon | failed | grok-4.6 / grok | 2026-08-20T19:21:48.916142+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-rj.3--mon/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-rj.3--mon-0 | active | grok-4.6 / grok | 2026-08-20T19:33:24.533373+00:00 | 0 | — | — |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-rj.1](../agents/bbugyi200.athena.sase-rj.1/README.md) | sase-rj hood | completed |
| [sase-rj.2](../agents/bbugyi200.athena.sase-rj.2/README.md) | sase-rj hood | completed |
| [sase-rj.4](../agents/bbugyi200.athena.sase-rj.4/README.md) | sase-rj hood | waiting |
| [sase-rj.land](../agents/bbugyi200.athena.sase-rj.land/README.md) | sase-rj hood | waiting |
