# Family: sase-11l.11.4

[Agent Hoods](../README.md) / [bbugyi200](../users/bbugyi200/README.md) / [athena](../users/bbugyi200/machines/athena/README.md) / [sase-11l](../users/bbugyi200/machines/athena/hoods/sase-11l/README.md) / sase-11l.11.4

Owner: `bbugyi200.athena` · Hood: `sase-11l` · Members: 5 · Bead: [sase-11l.11.4](https://github.com/sase-org/sase--beads/blob/main/pages/sase-11l/sase-11l.11.4.md)

## Lineage

```mermaid
flowchart TD
  n0["sase-11l.11.4--2 [active]"]
  n1["sase-11l.11.4--1 [active]"]
  n0 --> n1
  n2["sase-11l.11.4--plan [active]"]
  n0 --> n2
  n3["sase-11l.11.4--mon-0 [active]"]
  n0 --> n3
  n4["sase-11l.11.4--mon [active]"]
  n0 --> n4
```

The diagram is an optional enhancement; the ordered table below contains the same lineage in accessible text.

| Role | Agent | State | Model / provider | Timing | Commits | Prompt | Chat |
|---|---|---|---|---|---:|---|---|
| <a id="member-2"></a>2 | sase-11l.11.4--2 | active | grok-4.6 / grok | 2026-09-19T08:10:57.657546+00:00 | [1](../agents/bbugyi200.athena.sase-11l.11.4--2/README.md#commits) | [Prompt](../agents/bbugyi200.athena.sase-11l.11.4--2/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11l.11.4--2/chat.md) |
| <a id="member-1"></a>1 | sase-11l.11.4--1 | active | grok-4.6 / grok | 2026-09-19T07:53:26.608208+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-11l.11.4--1/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11l.11.4--1/chat.md) |
| <a id="member-plan"></a>plan | sase-11l.11.4--plan | active | grok-4.6 / grok | 2026-09-19T06:30:04.675086+00:00 | 0 | [Prompt](../agents/bbugyi200.athena.sase-11l.11.4--plan/prompt.md) | [Chat](../agents/bbugyi200.athena.sase-11l.11.4--plan/chat.md) |
| <a id="member-mon-0"></a>mon-0 | sase-11l.11.4--mon-0 | active | grok-4.6 / grok | 2026-09-19T07:59:48.246302+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11l.11.4--mon-0/chat.md) |
| <a id="member-mon"></a>mon | sase-11l.11.4--mon | active | grok-4.6 / grok | 2026-09-19T07:07:03.146276+00:00 | 0 | — | [Chat](../agents/bbugyi200.athena.sase-11l.11.4--mon/chat.md) |

## Commits

| Role | Repo | Commit | Subject | Committed |
|---|---|---|---|---|
| 2 | sase | [`388d516`](https://github.com/sase-org/sase/commit/388d5160308367121467539eb3114bc342833ffc) | feat(hold): delegate deadlock detection to shared core reachability | 2026-09-19 04:18:43 EDT |

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [sase-11l.11.1](bbugyi200.athena.sase-11l.11.1.md) (family · 7) | sase-11l.11 hood | active 7 |
| [sase-11l.11.2](bbugyi200.athena.sase-11l.11.2.md) (family · 5) | sase-11l.11 hood | active 5 |
| [sase-11l.11.3](bbugyi200.athena.sase-11l.11.3.md) (family · 3) | sase-11l.11 hood | active 3 |
| [sase-11l.11.5.1](bbugyi200.athena.sase-11l.11.5.1.md) (family · 7) | sase-11l.11 hood | active 7 |
| [sase-11l.11.5.land](bbugyi200.athena.sase-11l.11.5.land.md) (family · 3) | sase-11l.11 hood | active 3 |
| [sase-11l.11.5.land.f0](bbugyi200.athena.sase-11l.11.5.land.f0.md) (family · 3) | sase-11l.11 hood | active 1, completed 1, failed 1 |
| [sase-11l.11.land](bbugyi200.athena.sase-11l.11.land.md) (family · 3) | sase-11l.11 hood | active 3 |
| [sase-11l.1](bbugyi200.athena.sase-11l.1.md) (family · 3) | sase-11l hood | active 2, completed 1 |
| [sase-11l.10](bbugyi200.athena.sase-11l.10.md) (family · 11) | sase-11l hood | active 1, completed 4, failed 6 |
| [sase-11l.2](../agents/bbugyi200.athena.sase-11l.2/README.md) | sase-11l hood | active |
| [sase-11l.3](bbugyi200.athena.sase-11l.3.md) (family · 3) | sase-11l hood | active 2, completed 1 |
| [sase-11l.4](bbugyi200.athena.sase-11l.4.md) (family · 3) | sase-11l hood | active 2, completed 1 |
| [sase-11l.5](bbugyi200.athena.sase-11l.5.md) (family · 3) | sase-11l hood | active 3 |
| [sase-11l.5](../agents/bbugyi200.athena.sase-11l.5/README.md) | sase-11l hood | dismissed |
| [sase-11l.5.1.1](bbugyi200.athena.sase-11l.5.1.1.md) (family · 3) | sase-11l hood | active 2, completed 1 |
| [sase-11l.5.1.2](bbugyi200.athena.sase-11l.5.1.2.md) (family · 3) | sase-11l hood | active 3 |
| [sase-11l.5.1.2.1.1](../agents/bbugyi200.athena.sase-11l.5.1.2.1.1/README.md) | sase-11l hood | active |
| [sase-11l.5.1.2.1.2](../agents/bbugyi200.athena.sase-11l.5.1.2.1.2/README.md) | sase-11l hood | active |
| [sase-11l.5.1.2.1.3](../agents/bbugyi200.athena.sase-11l.5.1.2.1.3/README.md) | sase-11l hood | active |
| [sase-11l.5.1.2.1.4](../agents/bbugyi200.athena.sase-11l.5.1.2.1.4/README.md) | sase-11l hood | active |
| [sase-11l.5.1.2.1.land](bbugyi200.athena.sase-11l.5.1.2.1.land.md) (family · 3) | sase-11l hood | active 2, completed 1 |
| [sase-11l.5.1.2.1.land](../agents/bbugyi200.athena.sase-11l.5.1.2.1.land/README.md) | sase-11l hood | waiting |
| [sase-11l.5.1.3](bbugyi200.athena.sase-11l.5.1.3.md) (family · 3) | sase-11l hood | active 3 |
| [sase-11l.5.1.land](bbugyi200.athena.sase-11l.5.1.land.md) (family · 3) | sase-11l hood | active 3 |
| [sase-11l.6](../agents/bbugyi200.athena.sase-11l.6/README.md) | sase-11l hood | active |
| [sase-11l.7](../agents/bbugyi200.athena.sase-11l.7/README.md) | sase-11l hood | active |
| [sase-11l.8](../agents/bbugyi200.athena.sase-11l.8/README.md) | sase-11l hood | active |
| [sase-11l.9](../agents/bbugyi200.athena.sase-11l.9/README.md) | sase-11l hood | active |
| [sase-11l.land](bbugyi200.athena.sase-11l.land.md) (family · 3) | sase-11l hood | active 3 |
